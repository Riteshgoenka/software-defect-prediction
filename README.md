# Software Defect Prediction

This repository contains code related to the application of the k-Label Dependent Evolutionary Distance Weighting (kLDEDW) algorithm [1] to the Software Defect Prediction problem.

## Directory Layout

* `CVDP and CPDP`: Code for Cross Version and Cross Project Defect Prediction
  * `kLDEDW with distance measure based training set selection`: Defection prediction using the kLDEDW algorithm; training dataset - previous version for CVDP and a combination of two nearest datasets based on a chi-square statistic based distance measure $D$ for CPDP
  * `kLDEDW with nearest neighbor training set selection`: Defection prediction using the kLDEDW algorithm; training dataset - previous version for CVDP and collection of nearest datapoints for CPDP
  * `kNN`: Defection prediction using the k-Nearest Neighbor (k-NN) algorithm; training dataset - previous version for CVDP and a combination of two nearest datasets based on the distance measure D for CPDP
* `WPDP`: Code for Within Project Defect Prediction
  * `kLDEDW`: Defection prediction using the kLDEDW algorithm
  * `kNN`: Defection prediction using the k-NN algorithm
* `Data`: Defect datasets collected by Jureczko and Madeyski [2]
* `Training Data Selection`: Code for selecting datasets for CPDP based on the distance measure D
  * `select_training.py`: Code for selecting nearest datasets under the distance measure D
  * `format_data.py`: Code to read and preprocess the datasets

## Additional Remarks

* Each subdirectory in `CVDP and CPDP` and `WPDP` has the following structure:
  * `format_data.py`: Code to read and preprocess the datasets
  * `<algorithm>.py`: Algorithm for defect prediction - kLDEDW or k-NN
  * `run.sh`: Bash script for running defect prediction on all datasets
  * `Results`: Results obtained by running `run.sh`
* A sample command for running the kLDEDW algorithm with a combination of jedit-4.0.csv and jedit-4.1.csv as the training set and ant-1.3.csv as the test set is given below.
    ```
    python3 kLDEDW.py jedit-4.0.csv jedit-4.1.csv ant-1.3.csv
    ```

## References

[1] Daniel Mateos-García, Jorge García-Gutiérrez, & José C. Riquelme-Santos (2012). On the evolutionary optimization of k-NN by label-dependent feature weighting. Pattern Recognition Letters, 33(16), 2232–2238.

[2] Jureczko, M., & Madeyski, L. (2010). Towards Identifying Software Project Clusters with Regard to Defect Prediction. In Proceedings of the 6th International Conference on Predictive Models in Software Engineering. Association for Computing Machinery.
