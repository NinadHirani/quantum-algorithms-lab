# Quantum Algorithms Lab

A personal lab notebook for learning and implementing quantum algorithms, by **Ninad Hirani** (Computer Engineering, V.V.P. Engineering College, Rajkot).

It collects my Qiskit, Cirq and PennyLane work: first circuits, a full theory write-up of Shor's algorithm, QUBO optimisation with variational circuits, and solved assignments from the Qnickel quantum computing course (Simon's algorithm, Grover search for Max-Cut, classical gates, and an introduction to Cirq).

## What's inside

| Path | What it covers | Framework |
|---|---|---|
| `notebooks/01-QuantumAlgo.ipynb` | First circuit: Hadamard + measurement on the Aer simulator | Qiskit |
| `notebooks/QuantumAlgo/Shor_Algorithm_Basics.ipynb` | GCD, modular exponentiation and period finding, the classical core of Shor's algorithm | Python / NumPy |
| `notes/Shor-Algorithm.md` | Complete theory notes on Shor's algorithm (QFT, period finding, why it threatens RSA) | Notes |
| `notebooks/quantumoptimization/qubobypennylane.ipynb` | QUBO to Ising Hamiltonian mapping, solved variationally (1-variable, 2-variable and Max-Cut on a triangle graph) | PennyLane |
| `Qnickel/Assign_SimonSolByNH.ipynb` | Simon's algorithm: circuit setup, collecting y values, oracle construction | Qiskit |
| `Qnickel/Assign_GroverMaxCutSolByNH.ipynb` | Grover oracles for a marked state, 2-colouring and Max-Cut | Cirq |
| `Qnickel/Assign_ClassicalGatesSolByNH.ipynb` | Building classical logic gates from quantum gates | Qiskit |
| `Qnickel/Assign_IntroToCirqSolByNH.ipynb` | Introduction to Cirq circuits, moments and simulation | Cirq |
| `notebooks/Python/practice.ipynb` | Python and Qiskit warm-up practice | Python / Qiskit |
| `notebooks/QISKIT_TEMPLATE.ipynb` | Template for starting a new algorithm notebook | Qiskit |

## Getting started

```bash
git clone https://github.com/NinadHirani/quantum-algorithms-lab.git
cd quantum-algorithms-lab

# Conda (recommended)
conda env create -f environment.yml
conda activate quantum-algorithms-lab

# or pip
pip install -r requirements.txt

jupyter notebook
```

See [`QISKIT_SETUP.md`](QISKIT_SETUP.md) for kernel setup, standard imports and troubleshooting.

All notebooks run end to end on a local simulator (tested with Qiskit 2.x, Qiskit Aer 0.17, Cirq 1.7 and PennyLane 0.45). No quantum hardware account is needed.

## Related work

- [CVRP with QAOA](https://github.com/NinadHirani/Solving-the-Capacitated-Vehicle-Routing-Problem-Using-the-Quantum-Approximate-Optimization-Algorithm): research internship project solving the capacitated vehicle routing problem with the Quantum Approximate Optimization Algorithm.

## Author

Ninad Hirani · [GitHub](https://github.com/NinadHirani)
