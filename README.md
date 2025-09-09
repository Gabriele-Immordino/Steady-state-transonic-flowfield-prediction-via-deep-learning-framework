Deep Learning for Steady Transonic Flowfield Prediction
====================================================================

This script supports the paper:  
**"Steady-State Transonic Flowfield Prediction via Deep-Learning Framework"**  
Available at: [https://arc.aiaa.org/doi/abs/10.2514/1.J063545](https://arc.aiaa.org/doi/abs/10.2514/1.J063545)


Purpose:
--------
This code implements a fully connected neural network (FCNN) for predicting 3D steady aerodynamic flowfields (pressure and skin-friction) over wing-body configurations in the transonic regime. It integrates:

- Output-field regression using structured Cartesian encoding,
- Multi-feature flow representation including CP and shear components,
- Efficient evaluation over extended Mach–AoA design spaces.

Key Features:
-------------
- Dataset: CFD surface fields with [x, y, z, CP, CFx, CFy, CFz] and associated Mach and AoA values.
- Architecture: Dense neural network trained to map aerodynamic conditions to flowfield outputs.
- Evaluation: Assessed on BSCW, ONERA M6, and NASA CRM configurations.
- Output: 3D aerodynamic field predictions with accurate shock and separation detection.

Dependencies:
-------------
Install the required Python packages before running the scripts:

```bash
pip install numpy
pip install pandas
pip install tensorflow
pip install keras-tuner
pip install scikit-learn
pip install matplotlib
pip install chaospy
```
-------------
Ensure the following scripts are executed in the proper sequence:

1. **Data Preparation and Training (Main Framework)**

   ```bash
   main.ipynb
````

This is the principal implementation for generic steady-state flowfield prediction using supervised learning.

2. **Static Deformation Prediction (Application to Aeroelastic Case)**

   ```bash
   static_deformation.ipynb
   ```

   This script evaluates static aeroelastic twist deformation of the BSCW wing using predicted aerodynamic loads.

3. **Uncertainty Quantification (Application via NIPCE)**

   ```bash
   UQ_polynomial_chaos.ipynb
   ```

   Implements non-intrusive polynomial chaos expansion to propagate uncertainty in Mach and AoA through the trained network for BSCW test case.

Citation

If you use this code or dataset in your research, please cite:
G. Immordino, A. Da Ronch, and M. Righi.  
Steady-state transonic flowfield prediction via deep-learning framework.  
AIAA Journal, pages 1–17, 2024.  
https://doi.org/10.2514/1.J063545


Author: Gabriele Immordino

