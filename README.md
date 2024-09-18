Fuzzy Logic Crop Yield Prediction
This project uses a fuzzy logic system to predict crop yield based on inputs such as rainfall, temperature, and soil fertility. The system is built using the scikit-fuzzy Python library.

Features
- Fuzzy inference system based on rainfall, temperature, and soil fertility.
- Predicts the crop yield based on these inputs using fuzzy logic principles.
- Customizable membership functions and rules for precise modeling.

Dependencies
The following Python libraries are required:

- numpy
- scikit-fuzzy
You can install the dependencies using:

bash
Copy code
pip install numpy scikit-fuzzy
How it Works
Define Inputs (Antecedents):

Rainfall: Values range from 0 to 200 units.
Temperature: Values range from 0 to 50°C.
Soil Fertility: Values range from 0 to 100%.
Define Output (Consequent):

Crop Yield: Predicted output ranging from 0 to 100%.
Fuzzy Membership Functions:

The membership functions for each input and output variable are defined using triangular membership functions.
Fuzzy Rules:

The fuzzy logic system is governed by rules that determine how input variables influence the output.
Example Code Snippet
python
Copy code
import numpy as np
import skfuzzy as fuzz
from skfuzzy import control as ctrl

# Define input variables
rainfall = ctrl.Antecedent(np.arange(0, 201, 1), 'rainfall')
temperature = ctrl.Antecedent(np.arange(0, 51, 1), 'temperature')
soil_fertility = ctrl.Antecedent(np.arange(0, 101, 1), 'soil_fertility')

# Define output variable
crop_yield = ctrl.Consequent(np.arange(0, 101, 1), 'crop_yield')

# Define fuzzy membership functions
rainfall['low'] = fuzz.trimf(rainfall.universe, [0, 0, 100])
rainfall['medium'] = fuzz.trimf(rainfall.universe, [50, 100, 150])
rainfall['high'] = fuzz.trimf(rainfall.universe, [100, 200, 200])

# Continue defining membership functions for other variables...
Running the Script
Clone this repository.
Install the necessary dependencies.
Run the Jupyter notebook to see the fuzzy inference system in action.
bash
Copy code
jupyter notebook fuzzy_logic_devraj_khatiwada.ipynb
Customization
You can modify the input ranges, membership functions, or fuzzy rules to tailor the system to different crop yield prediction scenarios.

