# Quantum Computational Fluid Dynamics (QCFD)

## Stream Function Vorticity Method

Check out [this folder](https://github.com/Weidsn/Quantum_Computing_Collaboration/tree/main/Stream%20function%20vorticity).

Theory of [Streamfunction-Vorticity Formulation](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Stream%20function%20vorticity/streamfunction-vorticity.pdf). Gentle introduction to [Stream Function](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Stream%20function%20vorticity/Fluid_Mechanics_Lesson_10C_stream%20function.pdf).

Solving for [Lid Driven Cavity](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Stream%20function%20vorticity/LidDrivenCavity.ipynb) (work-in-progress).

## Quantum Lattice Boltzmann Method

Software Framework (python package) for building and evaluating Quantum Lattice Boltzmann Models: [QLBM](https://github.com/QCFD-Lab/qlbm).

Credit to [Călin A. Georgescu](https://orcid.org/0000-0002-8102-6389), [Merel A. Schalkers](https://orcid.org/0000-0001-7751-9060) and [Matthias Möller](https://orcid.org/0000-0003-0802-945X) from Delft University of Technology. 

## Qiskit

Qiskit is a python library for quantum computing, developed by IBM. Another one is PennyLane, with company based in Canada. 

You may check our my [qiskit installation guide with examples](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Qiskit/Qiskit_Installation_with_examples.ipynb).

### Qiskit Aer Simulator

Qiskit Aer is a classical simulator for quantum circuits. It is built on top of the Qiskit framework and provides a variety of simulation backends modeled on IBM's quantum computers.

## Linear Equation Solvers

### HHL Algorithm

Follow these links the check out the [theory of HHL](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/HHL%20textbook.md) and my [reading notes on HHL](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/HHL%20notes.md).

For qiskit implementation, see [Qiskit HHL tutorial](https://github.com/Qiskit/textbook/blob/aebdd2bc86ddb7a79dd8441d52c839d312ffafbb/notebooks/ch-applications/vqls.ipynb), obtained from the [qiskit textbook](https://github.com/Qiskit/textbook/tree/main), which contains deprecated qiskit codes, and community developed [HHL prototype](https://github.com/quantumapplicationlab/hhl-prototype?tab=readme-ov-file).

### VQLS Algorithm

Original paper on VQLS is paper [[5]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/Variational%20quantum%20linear%20solver.pdf), and here is a [reading note on VQLS](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/%5B5%5D%20VQLS.md).

For qiskit implementation, see my [VQLS implementation](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Qiskit/vqls_implementation.ipynb).

For tutorials, check out [PennyLane VQLS tutorial](https://pennylane.ai/qml/demos/tutorial_vqls), and [LinkedIn VQLS Tutorial](https://www.linkedin.com/posts/holger-marschall_variational-quantum-linear-solver-pennylane-activity-7059185416544866304-UsjT/). 

Check here for community developed [VQLS package](https://github.com/thegiantspaceman/VQLS) and [VQLS Prototype](https://github.com/QuantumApplicationLab/vqls-prototype/tree/main).

#### LCU decomposition (Linear Combination of Unitaries) in qiskit

Example of [LCU decomposition](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Qiskit/LCU_decomp.ipynb).

## Introduction to QCFD

A common example of a Computational Fluid Dynamics (CFD) problem is solving the Navier-Stokes equations. As mentioned in [1], the most critical step in obtaining a solution involves updating the pressure values at each point within the dynamic system. This iterative procedure is called "pressure correction."

Each iteration of pressure correction comes down to solving a linear system of equations that can be written in the form, $Ax = b$. There are two major bottlenecks.

The first is the computational cost of decomposing $A$ into a Linear Combination of Unitary matrices (LCU) so that we can encode $A$ using quantum gates.

The second is the cost of actually solving the linear system of equations $Ax = b$ and reading out the result. We may use quantum algorithms such has HHL, or variational hybrid quantum-classical algorithms (VQA), such as Variational Quantum Linear Solver (VQLS)
<sup>[[5]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Variational%20quantum%20linear%20solver.pdf)</sup>.

Both types of algorithm are constrained by quantum computers that are currently available, which are Noisy Intermediate Scale Quantum (NISQ) computers.

## Papers

#### [[1]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/A%20hybrid%20quantum-classical%20CFD%20methodology%20with%20benchmark%20HHL%20solutions.pdf) *A hybrid quantum-classical CFD methodology with benchmark HHL solutions* (June 2022)

Abstract: Decomposing CFD problems into a linear combination of unitariary matrices (LCU), whose coefficients can be computed using HHL. Quantum advantage of fault-tolerant computers is discussed.

[Notes](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/%5B1%5DHybrid_CFD.md) for [1]<br><br>

#### [[2]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/A%20Performance%20Study%20of%20Variational%20Quantum%20Algorithms%20for%20Solving%20the%20Poisson%20Equation%20on%20a%20Quantum%20Computer.pdf) *A Performance Study of Variational Quantum Algorithms for Solving the Poisson Equation on a Quantum Computer* (May 2023)

Abstract: Solving Poisson equations using a variational quantum algorithm (VQA), i.e., Variational Quantum Linear Solver (VQLS), on noisy intermediate scale quantum (NISQ) computers. Results were not promising. VQLS is further discussed in [5].

[Notes](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/%5B2%5D%20VQA%20for%20Poisson.md) for [2]
<br><br>

#### [[3]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/Hybrid%20quantum%20algorithms%20for%20flow%20problems.pdf) *Hybrid quantum algorithms for flow problems* (June 2023)

Abstract: Solving CFD problems by implementing HHL (referred to as a kind of Quantum Linear Systems Algorithm or in other words Quantum Linear Equation Solver QLES) with a discussion of Quantum Postprocessing Protocol (QPP), which concerns information extraction via quantum state measurements.

[Hand-written summary](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/Hybrid%20Quantum%20Algorithms%20for%20flow%20problems%20notes.pdf) and [notes](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/%5B3%5D%20Flow%20Problems.md) for [3]
<br><br>

#### [[4]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/Variational%20quantum%20algorithm%20for%20the%20Poisson%20equation.pdf) *Variational quantum algorithm for the Poisson equation* (2021)

Abstract: Solving Poisson equations using a variational quantum algorithm (VQA) that reduces the number of quantum measurements required on NISQ computers. <br><br>

#### [[5]](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Papers%20on%20Computational%20Fluid%20Dynamics/Variational%20quantum%20linear%20solver.pdf) *Variational quantum linear solver* (2023)

Abstract: As a kind of variational quantum algorithm (VQA), introducing the Variational Quantum Linear Solver (VQLS) to find a proximate solution to the problem $A {| x \rangle} = { |b \rangle}$ on NISQ computers.

[Notes](https://github.com/Weidsn/Quantum_Computing_Collaboration/blob/main/Reading%20Notes%20and%20Summaries/%5B5%5D%20VQLS.md) for [5]
