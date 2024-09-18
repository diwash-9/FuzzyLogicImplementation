## Fuzzy Logic Crop Yield Prediction

This project uses a fuzzy logic system to predict crop yield based on rainfall, temperature, and soil fertility using the `scikit-fuzzy` library.

### Features
- Fuzzy inference system based on rainfall, temperature, and soil fertility.
- Predicts crop yield using fuzzy logic principles.
- Customizable membership functions and rules.

### Dependencies
The following Python libraries are required:

- `numpy`
- `scikit-fuzzy`

```bash
pip install numpy scikit-fuzzy
```
### How It Works

#### Inputs (Antecedents):
- **Rainfall**: 0 to 200 units.
- **Temperature**: 0 to 50°C.
- **Soil Fertility**: 0 to 100%.

#### Output (Consequent):
- **Crop Yield**: 0 to 100%.

#### Fuzzy Membership Functions:
Membership functions for each variable are defined using triangular functions.

#### Fuzzy Rules:
The system is governed by rules that determine how inputs affect the output.

### Example Code Snippet

```python
import numpy as np
import skfuzzy as fuzz
from skfuzzy import control as ctrl

# Define input variables
rainfall = ctrl.Antecedent(np.arange(0, 201, 1), 'rainfall')
temperature = ctrl.Antecedent(np.arange(0, 51, 1), 'temperature')
soil_fertility = ctrl.Antecedent(np.arange(0, 101, 1), 'soil_fertility')

# Define output variable
crop_yield = ctrl.Consequent(np.arange(0, 101, 1), 'crop_yield')

# Define fuzzy membership functions for 'rainfall'
rainfall['low'] = fuzz.trimf(rainfall.universe, [0, 0, 100])
rainfall['medium'] = fuzz.trimf(rainfall.universe, [50, 100, 150])
rainfall['high'] = fuzz.trimf(rainfall.universe, [100, 200, 200])
```

### Running the Script

1. Clone the repository.
2. Install the dependencies.
3. Run the Jupyter notebook to see the fuzzy inference system in action.

```bash
jupyter notebook fuzzy_logic_devraj_khatiwada.ipynb
```









