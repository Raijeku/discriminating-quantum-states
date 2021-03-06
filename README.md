[![GitHub license](https://img.shields.io/github/license/Raijeku/discriminating-quantum-states)](https://github.com/Raijeku/discriminating-quantum-states/blob/main/LICENSE)
[![arXiv](https://img.shields.io/badge/arXiv-2112.00313-red)](https://arxiv.org/abs/2112.00313)


# Discriminating Quantum States with Quantum Machine Learning

This repository contains all the source code used to generate results presented in "[Discriminating Quantum States with Quantum Machine Learning](https://qce.quantum.ieee.org/posters-program/#ps14)".

## Contents

* ``qkmeans.py``: Module for quantum k-means algorithm with a class containing sk-learn style functions resembling the k-means algorithm.
* ``dataset.ipynb``: Code for retrieval of in-phase and quadrature (IQ) signal data from IBMQ Bogota after applying pulses that drive qubits to the |0> and |1> states. Arrays of signal data are retrieved from |00>, |01>, |10> and |11> prepared state schedules for all qubit couples in a quantum device.
* ``classical_correlation.ipynb``: Classical correlation analysis for IBMQ Bogota using Pearson Correlation coefficients and the k-means algorithm.
* ``quantum_correlation.ipynb``: Quantum correlation analysis for IBMQ Bogota using Pearson Correlation coefficients and the qk-means algorithm.

## Usage example
   
Example code for use of the qk-means algorithm:

```python
import numpy as np
import pandas as pd
from qkmeans import *

backend = IBMQ.load_account().get_backend('ibmq_qasm_simulator')
X = pd.DataFrame(np.array([[1, 2], [1, 4], [1, 0], [10, 2], [10, 4], [10, 0]]))
qk_means = QuantumKMeans(backend, n_clusters=2, verbose=True, map_type='angle')
qk_means.fit(X)
print(qk_means.labels_) 
```

## Authors

David Quiroga, Prasanna Date, Raphael Pooser.

If you are doing any research using this source code, please cite the following paper:

> David Quiroga, Prasanna Date, Raphael Pooser. Discriminating Quantum States with Quantum Machine Learning. arXiv, 2021. [arXiv:2112.00313](https://arxiv.org/abs/2112.00313)
      
## License

This source code is free and open source, released under the Apache License, Version 2.0.
   
