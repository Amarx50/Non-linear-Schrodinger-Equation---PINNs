# Non-linear-Schrodinger-Equation---PINNs

### Overview

The Nonlinear Schrodinger Equation (NLS) is a partial differential equation seen in many areas of physics such as optics. This project explores the use of Physics-Informed Neural Networks (PINNs) for solving the NLS, and comparing the results to the classical solver - the Split-Step Fourier Method. Both techniques are clearly explained and completed methodically within this project. The PINN is trained through enforcing the boundary and initial conditions, as well as the residual error into the loss function. 

### Method

A bright soliton initial condition is used, which theoretically should maintain amplitude and constant propagation speed as time elapses. Firstly, the Split-Step Fourier Method is implemented, serving as a reference for the PINN. Proceeding this, the PINN is coded using TensorFlow, taking spatial and temporal coordinates as input, and outputs the real and imaginary components of the wavefunction. In line with regular neural network training, the goal is to minimise the loss function. Automatic differentiation is used to compute the spatial and temporal derivatives, and the Adam optimiser is used during training. Finally, the PINN is compared with the SSFM to visualise the difference between the two methods. 

### Results

The trained PINN succesfully reproduced the overall soliton shape, and closely matched the propagation speed when comparing to the SSFM solution. However, a gradual reduction in the soliton amplitude is observed at later times for the PINN solution, highlighting a common limitation of PINNs: the conservation laws are enforced indirectly through the loss function rather than preserved exactly, whereas the SSFM preserves these exactly. Despite this limitation, the PINN is still able to create relatively accurate solutions that can be improved from increasing sample size, training 'epochs' and enforcing more laws into the loss function. If I were to extend this project, I would do exactly this, however doing so is costly and takes a lot of time to run.

### Libraries and Tools

Python, Tensorflow, NumPy, Matplotlib

