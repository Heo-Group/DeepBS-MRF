# DeepBS-MRF
Bloch-Simulator-Driven Deep Recurrent Neural Network (DeeoBS) for Magnetization Transfer Contrast MR Fingerprinting and CEST Imaging

This repository contains the TensorFlow codes to facilitate reproducibility of semisolid MTC and water parameter estimation as described in 
"Bloch-Simulator-Driven Deep Recurrent Neural Network for Magnetization Transfer Contrast MR Fingerprinting and CEST Imaging" and for 
further developments in CEST imaging. Here, pretrained models and numerical phantom data are provided to estimate tissue parameters. 
Pretrained models can also be used for estimation of in-vivo tissue parameters from MTC-MRF signals. However, it requires specific sequence 
for acquisition of MTC-MRF signals, details are mentioned in the paper (<https://doi.org/10.1002/mrm.29748>).

![Concept_figure](https://user-images.githubusercontent.com/122308855/211408433-880deae2-bf03-4465-94fa-ccc62554b90a.jpg)

### Template command

This file helps in testing of deep Bloch simulator, deep Bloch simulator to generate two-pool MTC reference signals at 1 uT and 1.5 uT, and reconstruction network.
```
--run Test.ipynb
```

This file helps to train the dataset, you need to have ground truth tissue parameters and Zref signals at 1uT and 1.5 uT. To demonstrate, we used 10K dataset to train neural network for 40 epochs, originally, neural network was trained for 40 million dataset, 
while selection of number of epochs was based on minimum error between acquired MTC-MRF and synthesized MTC-MRF.
```
--run Train.ipynb
```

MTC-MRF data and corresponding ground truth tissue parameters are provided in folder: data
Numerical phantom data is provided in folder: data/numerical_phantom
Architectures of deep learning-based Bloch simulation is provided in folder: deepBS_networks
Pretrained neural networks are in folder: saved_models
