# DeepEnsm


## This is the readme file that contains the guidelines and information about the compilation the code of the following paper

**Paper Name:-** [Ensembling of Gene Clusters utilizing Deep Learning and Protein-protein Interaction Information](https://ieeexplore.ieee.org/document/8721175)
* **Authors:** Pratik Dutta<sup>1</sup>, Sriparna Saha<sup>1</sup>, Sraansh Chopra<sup>1</sup> and Varnika Miglani<sup>2</sup>
* **Affiliation:** <sup>1</sup>Indian Institute of Technology Patna, India, <sup>2</sup>Samsung R&D Institute India-Noida
* **Accepted(8th May, 2019):** [IEEE/ACM Transactions on Computational Biology and Bioinformatics](https://www.computer.org/csdl/journal/tb)
* **Corresponding Author:** [Pratik Dutta](http://www.iitp.ac.in/~pratik.pcs16/) (pratik.pcs16@iitp.ac.in ) 

If you find this code or the article useful, consider citing our work: 
```bash
@article{dutta2019ensembling,
  title={Ensembling of Gene Clusters utilizing Deep Learning and Protein-protein Interaction Information},
  author={Dutta, Pratik and Saha, Sriparna and Chopra, Saraansh and Miglani, Varnika},
  journal={IEEE/ACM transactions on computational biology and bioinformatics},
  year={2019},
  publisher={IEEE}
}
```



## Prerequisities
* **[Python 2.7+](https://www.python.org/downloads/release/python-2713/)**
* **[sklearn](https://scikit-learn.org/stable/install.html)**
* **[matplotlib 2.0+](https://matplotlib.org/users/installing.html)**
* **[mpl_toolkits](https://matplotlib.org/2.0.2/mpl_toolkits/index.html)**
* **[numpy 1.10+](https://pypi.org/project/numpy/)**

## Preprocessed_dataset
This folder contains five preprocessed datasets which are used as the input of the proposed MOO-based clustering algorithm.   


## MOO

This folder contains the python code of the proposed MOO-based clustering. Use `terminal`(for linux users) and goto the '1. MOO-based clustering' folder. Then complie the code by following commands

```bash
cd examples
```
Write the **_PATH DESCRIPTION_** of the `dataset` in line number **27** of the **`main.py`**


```bash
python main.py <initial_population_size> <number_of_generation>
```

**Output:** Generate a file named **`non_dominated_solutions.txt`** that contains all the cluster information.


## Approach 2

This folder contains `.ipynb` (Jupyter Notebok) files for creating a set of disconnected walks which further used to generate the `labelled dataset`. This `labelled dataset` is used as the training dataset for the proposed neural network models. The main components of the folder are 

* **`BCLL_FuLL_Labels`** labels of the all non-dominated solutions for B-CLL dataset 
* **`algorithm1.ipynb`** This `jupyter notebook` file takes all non-dominated solutions as the input and gives weighted coincidence matrix. This coincidence matrix is fed to `algorithm 1` and it gives a set of disconnected walks. The set of the disconnected is save in `disconnected_walk.txt`
* **`create_train_test.ipynb`** This `jupyter notebook` generates `labeled_file.txt` and `unlabeled_file.txt`. 




## NN
This folder contains `.ipynb` files for training model which are used to generate final consensus partitionings for approach 2. For better use you can use `jupyter notebook` to run the files. The developed deep learning models are

* `NN Model.ipynb`  [PyTorch](https://pytorch.org/) implementation of the proposed multi-layer perceptron with two hidden layers 
* `CNN Model.ipynb` [PyTorch](https://pytorch.org/) implementation of the proposed convolutional neural network
* `Label Script.ipynb` is used to combine the originally labeled gene expressions and model labeled gene expressions into one file for further metric evaluations (BHI and BSI). 
* `BHI_labels_CNN.txt` and `BHI_labels_NN_2Hidden.txt` are the labels assigned to the unlabeled gene expressions by the trained models plus the originally labeled gene expression profiles. 
* `trained_model_10000_epochs.pt`, `trained_model_10000_epochs_2.pt`, `trained_model_10000_epochs_3.pt`, `trained_model_CNN_10000_epochs_1.pt`, `trained_model_CNN_10000_epochs_2.pt` files are the weights and bias matrices that are obtained after training the above models.



## Contribution
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
