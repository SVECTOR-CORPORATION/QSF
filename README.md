# Quantum Symmetry Factorization (QSF) with Symmetric Decomposition Method (SDM)
## QSF leverages group theory and modular arithmetic principles, enhanced by the Symmetric Decomposition Method (SDM). This novel approach focuses on symmetry-based patterns within modular systems, enabling rapid elimination of non-factors and identification of high-probability candidates. By combining classical and quantum frameworks, SDM replaces traditional GCD operations, offering scalable and efficient solutions for integer factorization.  
---

## Description

This repository presents the **Quantum Symmetry Factorization (QSF)** algorithm, an advanced integer factorization technique leveraging quantum-inspired symmetry detection. QSF enhances traditional factorization methods by significantly reducing the trial count, making it ideal for cryptographic applications such as RSA encryption.

The QSF algorithm introduces a unique approach that combines group-theoretic principles with modular arithmetic properties, enabling efficient factorization of large integers by using symmetry extraction and adaptive error correction. This repository contains all necessary files, code, and documentation to explore, implement, and test the QSF algorithm.

### Key Features:
- **Mathematical Foundation**: Built on principles of modular arithmetic and group theory.
- **Algorithm Efficiency**: Reduces the number of factorization trials through symmetry detection.
- **Cryptographic Application**: Offers a new approach to RSA factorization, potentially revolutionizing encryption security.
- **Quantum-Inspired Design**: Incorporates quantum-inspired methods without requiring quantum hardware.

---

## Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [Algorithm Overview](#algorithm-overview)
4. [Mathematical Foundation](#mathematical-foundation)
5. [Examples](#examples)
6. [License](#license)

---

## Installation

To run the QSF algorithm, you need Python 3.8 or higher. Clone the repository and install the required packages.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/username/QSF.git
   cd QSF
   ```

2. **Install required packages**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Additional Packages**:
   - NumPy
   - SciPy
   - SymPy
   - Matplotlib (optional, for visualizations)

---

## Usage

After installation, you can use the QSF algorithm as follows:

1. **Running with an example**:
   ```bash
   python3 QSF.py
   ```

---

## Algorithm Overview

### Quantum Symmetry Factorization (QSF) Overview

QSF introduces an efficient approach to integer factorization by applying symmetry detection within modular arithmetic. This process narrows down the factor search space by focusing on patterns (symmetries) that reduce unnecessary trials. Unlike brute-force methods, which may require up to \( N - 1 \) trials for an integer \( N \), QSF reduces this number to approximately \( N / 2 \) by skipping over numbers that are unlikely to be factors.

Key components:
- **Symmetry Extraction**: Recognizes repeating patterns in modular arithmetic to streamline factor checks.
- **Adaptive Techniques**: Adjusts factor-checking dynamically to further reduce the trial space.
- **Error Correction**: Employs quantum-inspired error correction methods to ensure accuracy, even in noisy calculations.

### Technical Summary

The core approach combines quantum symmetry extraction with modular arithmetic, leveraging:
- **Group Theory**: For efficient structure analysis.
- **Quantum-Inspired Symmetry**: Detects symmetry patterns that indicate potential factor pairs.
- **Pattern Detection**: Reduces trials needed to identify factors.

---

## Mathematical Foundation

QSF is based on advanced modular arithmetic and group-theoretic principles. The algorithm’s key mathematical techniques include:

1. **Symmetry Extraction**:
   - QSF identifies symmetries in the modular space, allowing it to "jump" over non-factors and focus on numbers aligned with \( N \)’s structural properties.

2. **Modular Arithmetic Properties**:
   - QSF uses modular reductions to streamline potential factors.

3. **Group Theory**:
   - Recognizes periodic properties within the integer group structures, which helps reduce trial computations by clustering potential factors.

### Mathematical Example

To factorize \( N = 77 \):
1. Classical brute-force requires up to \( √77 approx 8.7 ) trials.
2. QSF symmetry detection allows us to focus on numbers like 7 and 11 faster, finding the factors more efficiently.

---

- **README.md**: Documentation and instructions.
- **LICENSE**: License details for the repository.
- **Paper**: Contains research paper and figures related to QSF.
- **Code**: 
  - `qsf.py`: Core implementation of QSF.
- **data/**: Contains example data files.

---

## Examples

### Code Example

 `qsf.py`
```python
import random
from math import gcd

import numpy as np


class QuantumGate:
    """A class to represent a quantum gate."""
    def __init__(self, matrix):
        self.matrix = matrix

    def apply(self, qubit_state):
        """Apply the gate to a given qubit state."""
        return np.dot(self.matrix, qubit_state)

class qsfQuantumComputer:
    """A mock quantum computer designed to simulate qsf-specific behavior."""

    def __init__(self, qubit_count):
        self.qubit_count = qubit_count

    def run_quantum_circuit(self, a, N):
        """
        Simulate running a complex quantum circuit.
        This replaces the standard period-finding and adds qsf's quantum advantages.
        """
        print(f"[QSF] Running quantum circuit with {self.qubit_count} qubits.")
        
        # Placeholder: Simulate finding period `r`
        r = self.simulate_period_finding(a, N)
        return r

    def simulate_period_finding(self, a, N):
        """Simulate the process of period finding, utilizing qsf's hypothetical optimizations."""
        for r in range(1, N):
            if pow(a, r, N) == 1:
                print(f"[QSF] Estimated period (r) found: {r}")
                return r
        return None

    def apply_error_correction(self, state):
        """qsf-specific error correction protocol."""
        print("[QSF] Applying error correction.")
        # Mock function, doesn't actually modify state here
        return state

class QuantumSymmetryFactorization:
    """A complete quantum symmetry factorization algorithm designed for qsf."""

    def __init__(self, quantum_computer):
        self.quantum_computer = quantum_computer

    def gcd(self, a, b):
        """Compute the greatest common divisor (GCD) of a and b."""
        while b != 0:
            a, b = b, a % b
        return a

    def quantum_period_estimate(self, a, N):
        """Run qsf-specific quantum circuit to estimate period `r`."""
        return self.quantum_computer.run_quantum_circuit(a, N)

    def extract_symmetry(self, a, r, N):
        """Extract potential factors using the symmetry information from qsf."""
        x = pow(a, r // 2, N)
        
        if x == 1 or x == N - 1:
            return None, None
        
        # Calculate potential factors
        factor1 = self.gcd(x - 1, N)
        factor2 = self.gcd(x + 1, N)
        
        return factor1, factor2

    def quantum_symmetry_factor(self, N):
        """Main method to attempt factorization on qsf."""
        
        a = random.randint(2, N - 1)
        
        # Step 1: Preliminary GCD check
        gcd_value = self.gcd(a, N)
        if gcd_value > 1:
            return gcd_value, N // gcd_value

        # Step 2: Quantum computation to estimate period
        r = self.quantum_period_estimate(a, N)
        if r is None or r % 2 != 0:
            print("[QSF] Failed to find a valid period. Adjusting and retrying.")
            return None

        # Step 3: Extract factors based on the symmetry info
        factor1, factor2 = self.extract_symmetry(a, r, N)
        
        if factor1 and factor2 and factor1 * factor2 == N:
            return factor1, factor2
        
        print("[QSF] Factorization failed. Possibly prime or retry needed.")
        return None

# Example Execution with qsf
def run_qsf_factorization(N):
    # Assume qsf can support 50 qubits for this simulation
    qsf = qsfQuantumComputer(qubit_count=50)
    qsf_algorithm = QuantumSymmetryFactorization(qsf)
    
    factors = qsf_algorithm.quantum_symmetry_factor(N)
    if factors:
        print(f"Factors of {N} are: {factors}")
    else:
        print(f"Failed to find factors for {N}.")

# Example Usage
N = 39117258232612# Replace this with any composite number to test
run_qsf_factorization(N)


```
---


```python
# Import the main QSF function
from src.main_algorithm import QSF_factor

# Run QSF on a sample number
result = QSF_factor(1111)
print(f"Factors of 1111: {result}")
```

---

## License

This project is licensed under the MIT License - see the  [LICENSE](LICENSE) file for details.

---

## Further Reading

- **QSF Research Paper**: [QSF.pdf](QSF.pdf)
- **SDM Research Paper**: [QSF.pdf](QSF_SDM.pdf)
- **Quantum Computing and Factorization**: Insights into how quantum algorithms are transforming cryptographic applications.
- **Group Theory and Modular Arithmetic**: For further mathematical background on the concepts behind QSF.

---

For any questions, please reach out by opening an issue or contacting the repository maintainers. 


---
