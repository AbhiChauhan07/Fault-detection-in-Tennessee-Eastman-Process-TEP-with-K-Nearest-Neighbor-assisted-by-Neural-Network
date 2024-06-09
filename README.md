## Motivation of FDD of TEP dataset 
+ Fault Detection and Diagnosis (FDD) is one of the critical aspects of the chemical Industry as it reduces unprecedented shutdown losses as well as optimizing the losses and cost. Main Goal of the project is to find the fault based on the classification techniques taught in class. The pipeline of the project is to first apply PCA (Principal Component Analysis) to extract the features. Then apply Q-statistics and T2 statistics for further information of the dataset. Then we will use advanced techniques such as Logistic Regression, KNN (K-nearest neighbor) and NN (Nural Network) to detect the fault.
+ KNN motivated by NN is novelty approach used in this project based on the similar ideas available in literatures (Eslamloueyan, 2011). The basic flow of this model is that we gave training dataset features as input to the K-Means clustering for the training data and assign each sample to one of the nclusters clusters. The same clustering model is then used to predict cluster memberships for the test data. The same clustering model is then used to predict cluster memberships for the test data. Now we will give inputs to the NN model. Train dataset is the training feature matrix and output of the train (cluster_membership_train)2 is the array of cluster assignments obtained from K-Means. The cluster memberships are used as labels for training a neural network.

![image](https://github.com/AbhiChauhan07/Fault-detection-in-Tennessee-Eastman-Process-TEP-with-K-Nearest-Neighbor-assisted-by-Neural-Network/assets/156859411/bb7ad06e-a9b5-4505-91fc-c4d0888e1705)

`Figure 1.` Precision matrix of LR, KNN, NN, KNN+NN

|                         | LR | KNN | NN | KNN+NN |
|-------------------------| -- | --- | -- | ------ |
|Test Accuracy Percentage |36% |62% |89% |**98%**|

This data analysys concluse that, accuracy result was compared from the publish literature by Pangun et. (Pangun Park, 2019) with similar dataset which also excluded the dataset of fault 3, 9, 15. Pangun et. (Pangun Park, 2019) all worked with all the simulationRun (500/500) where as this project only include first 50 simulationRun (50/500). Pangun et. all (Pangun Park, 2019)used the LSTM (long short-term memory) model and DCNN (Deep Convolutional Neural Network) for fault detection. KNN+NN model got **21.4%** more accuracy than the DCNN model and 6.1% more accurate than LSTM. Hence, proposed approach KNN+NN model is superior3 with limited dataset of TEP process and fault exclusion of 3,9,15.

| Sr | Model | SimulationRun | Faults excluded for FDD | Accuracy Percentage |
| -- | ----- | ------------- | ----------------------- | ------------------- |
|1 | KNN + NN |50 |3, 9, 15|**98.0%**|
|2. |LSTM (Pangun Park, 2019) (Ilong short-term memory) | 500 | 3, 9, 15 | 91.9% |
|3.| DCNN (Pangun Park, 2019) (Deep Convolutional Neural Network) | 500 | 3, 9, 15 | 76.4%|
