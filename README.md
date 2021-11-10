# Discriminating Quantum States with Quantum Machine Learning

This repository contains all the source code used to generate results presented in "[Discriminating Quantum States with Quantum Machine Learning](https://qce.quantum.ieee.org/posters-program/#ps14)".

## Contents

* ``qkmeans.py``: Module for quantum k-means algorithm with a class containing sk-learn style functions resembling the k-means algorithm.
* ``classical_correlation.ipynb``: Classical correlation analysis for the IBMQ Bogota device using Pearson Correlation coefficients and the k-means algorithm.
* ``quantum_correlation.ipynb``: Quantum correlation analysis for the IBMQ Bogota device using Pearson Correlation coefficients and the qk-means algorithm.

## Usage example
   
Example code for use of the qk-means algorithm:

```python
import numpy as np
import pandas as pd
from qkmeans import *

backend = Aer.get_backend('qasm_simulator')
X = pd.DataFrame(np.array([[1, 2], [1, 4], [1, 0], [10, 2], [10, 4], [10, 0]]))
qk_means = QuantumKMeans(backend, n_clusters=2, verbose=True)
qk_means.fit(X)
print(qk_means.labels_) 
```

## Authors

David Quiroga, Prasanna Date, Raphael Pooser.

If you are doing any research using this source code, please cite the following paper:

  David Quiroga, Prasanna Date, Raphael Pooser. Discriminating Quantum States with Quantum Machine Learning. IEEE International Conference on Rebooting Computing, 2021.
      
## License

This source code is free and open source, released under the Apache License, Version 2.0.
   
