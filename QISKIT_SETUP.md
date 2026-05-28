# Qiskit Setup Guide

## Environment Setup

Your quantum algorithms lab is configured with Qiskit. Follow these steps to get started:

### 1. Install Dependencies

Using Conda (recommended):
```bash
conda env create -f environment.yml
conda activate quantum-algorithms-lab
```

Using pip:
```bash
pip install -r requirements.txt
```

### 2. Verify Installation

Run this in Python to verify Qiskit is installed:
```python
import qiskit
print(qiskit.__version__)
```

### 3. Jupyter Setup

Install Jupyter kernel for the environment:
```bash
python -m ipykernel install --user --name quantum-algorithms-lab --display-name "Quantum Lab"
```

## Standard Qiskit Imports

Each notebook includes these standard imports:

```python
import qiskit
from qiskit import QuantumCircuit, QuantumRegister, ClassicalRegister, transpile
from qiskit_aer import AerSimulator
from qiskit.visualization import plot_histogram, plot_bloch_multivector
import matplotlib.pyplot as plt
import numpy as np

# Initialize simulator
simulator = AerSimulator()
```

## Notebooks

### `notebooks/Python/practice.ipynb`
Python fundamentals practice notebook with Qiskit environment setup.

### `notebooks/QuantumAlgo/01-Shor.ipynb`
Implementation and visualization of Shor's algorithm using Qiskit.

## Common Qiskit Patterns

### Create and Run a Circuit
```python
# Create circuit
qc = QuantumCircuit(2, 2)  # 2 qubits, 2 classical bits
qc.h(0)  # Hadamard gate
qc.cx(0, 1)  # CNOT gate
qc.measure([0, 1], [0, 1])

# Transpile for simulator
compiled = transpile(qc, simulator)

# Run and get results
result = simulator.run(compiled, shots=1000).result()
counts = result.get_counts()

# Visualize
plot_histogram(counts)
```

### Visualize Circuits
```python
qc.draw("mpl")  # Matplotlib (default)
qc.draw("text")  # Text representation
```

## Resources

- [Qiskit Documentation](https://docs.quantum.ibm.com/)
- [Qiskit Textbook](https://qiskit.org/textbook/)
- [IBM Quantum](https://quantum.ibm.com/)

## Troubleshooting

**Issue**: Kernel not found in Jupyter
- Solution: Reinstall ipykernel: `python -m ipykernel install --user --name quantum-algorithms-lab`

**Issue**: Qiskit import errors
- Solution: Update Qiskit: `pip install --upgrade qiskit qiskit-aer`

**Issue**: Visualization not displaying
- Solution: Ensure matplotlib is installed: `pip install matplotlib`
