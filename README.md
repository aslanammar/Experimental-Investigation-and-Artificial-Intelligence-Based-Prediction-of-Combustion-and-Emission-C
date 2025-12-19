# [[Artificial Intelligence-Assisted Experimental Study on the Effects of Dibutyl Maleate Additive Under Varying Injection Timings in Compression Ignition Engines
]](https://github.com/aslanammar/Experimental-Investigation-and-Artificial-Intelligence-Based-Prediction-of-Combustion-and-Emission-C)
(https://github.com/aslanammar/Experimental-Investigation-and-Artificial-Intelligence-Based-Prediction-of-Combustion-and-Emission-C)
Machine learning-based prediction of combustion characteristics in diesel engines.

## Models

Three deep learning architectures are implemented:

| Model | Architecture |
|-------|-------------|
| ANN | Dense(128→64→32→16→1) with Dropout(0.2) |
| CNN | Conv1D(64→32) + Dense(64→32→1) |
| LSTM | LSTM(64→32) + Dense(16→1) |

## Installation

```bash
pip install -r requirements.txt
```

## Usage

```python
from train import main

results = main(
    data_path="your_data.xlsx",
    input_features=['CA', 'Angle'],
    target_column='Pressure'
)
```

## Data Format

Excel file with columns:
- `CA`: Crank Angle (°CA)
- `Angle`: Injection Timing (°CA bTDC)
- `target`: Output variable (Pressure/HRR/Temperature)

## Training Parameters

| Parameter | Value |
|-----------|-------|
| Train/Test Split | 80/20 |
| Normalization | MinMaxScaler |
| Optimizer | Adam (lr=0.001) |
| Loss | MSE |
| Max Epochs | 200 |
| Early Stopping | patience=20 |
| Batch Size | 32 |

## License

MIT License
