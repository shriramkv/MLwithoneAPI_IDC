# Intel oneAPI Optimized Code Examples Repository <img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/4c8933b7-c1f1-400e-a1aa-cb30f656fa0d" height="60" width="60"><br>

## Welcome to the Intel oneAPI Optimized Code Examples Repository!

![1Data Analyst](https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/c6fe0679-e6e8-426d-90e0-5e6594088c97)

This repository contains optimized code examples that utilize various libraries from Intel's oneAPI toolkit. The three code files included in this repository demonstrate the usage of the following libraries:


#### ✅oneDAL (oneAPI Data Analytics Library) - oneDAL.ipynb<br>
#### ✅oneDNN (oneAPI Deep Neural Network Library) - oneDNN.ipynb<br>
#### ✅XGBoost with oneAPI - XGB.ipynb<br>

# Intel Developer Cloud 
To gain access to a wealth of resources, discussions, and support related to Intel's oneAPI toolkit, you can create an Intel Developer Zone (IDZ) account using the attached documents:
# Creating an IDC Account Guide: <a href="https://youtu.be/PhzlMQ8-GE4"><img src="https://github.com/shriramkv/SYCLwithIDC/assets/72274851/693730f3-cda3-4a02-9c63-5b3ac1838ad7" height="70" width="70"></a>

## Step by Step Guidelines for setting up the IDC and to launch the Jupyter Notebook.

<details>
<summary><h2>How to Run</h2><img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/a8f61ebf-4f8f-48f7-be47-8e8fcb7c0a13" height="60" width="60"></summary>




### 1.	Generate an ssh key using the command ssh-keygen in the power shell as an administrator. 

### 2.	Open the generated key file using notepad and copy the contents of the file.(C:\Users\<<username>>\.ssh is the path - file name is id_rsa.pub, use the command notepad id_rsa.pub) 

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/4f51e91c-be8a-461b-8292-38b147f0c342)<br>
![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/f049dd0d-c001-48d2-9cad-3623b723c98f)<br>


### 3.	Nextly login or register into the Developer Cloud and add the key under the profile section. https://scheduler.cloud.intel.com/

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/dd2308d9-5be6-4de4-82f6-e202741ad62b)


### 4.	Open .ssh folder and create a config file with the below commands:
Host myidc <br>
Hostname idcbetabatch.eglb.intel.com <br>
User uXXXXXX #← Request "scheduled access" at https://scheduler.cloud.intel.com/#/systems" to get your user identifier. <br>
IdentityFile ~/.ssh/id_rsa <br>
#ProxyCommand ncat --proxy YourProxy:XXXX %h %p --proxy-type socks5 %h %p  ## Uncomment if necessary <br>
ServerAliveInterval 60 <br>
ServerAliveCountMax 10 <br>
StrictHostKeyChecking no <br>
UserKnownHostsFile=/dev/null <br>

### 5.	On Powershell type `ssh myidc` to connect to your head node instance. This will enable you to be authenticated. 

### 6.	Next to connect to an interactive node type in the below command:
`srun --pty bash` <br>
`source /opt/intel/oneapi/setvars.sh` <br>

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/8d834f65-5a6d-4f96-8d3f-660f8f664097)
![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/e3346e85-8ef6-4c54-a1f4-a500374c8c24)


This will get the batch node activated! You will see this clearly in the powershell terminal. u***@idc-beta-batch-head-node would get changed to u***@idc-beta-batch-pvc-node
### 7.	Configure your shell using the command conda init bash

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/0639e4d6-ef69-4370-bae8-f3f38503d7b9)<br>

### 8.	Close the existing instance to make sure that the configuration changes reflect using the command exit

#### This will get the batch node activated! You will see this clearly in the powershell terminal. u***@idc-beta-batch-head-node would get changed to u***@idc-beta-batch-pvc-node

### 9.	You are taken back to the head node again, connect to the interactive node again by repeating Step6 again.

### 10.	To check the available environments type in the command conda env list

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/41f9f009-743b-4c06-9807-1932c6b7b843)<br>


### 11.	Choose the environment of your choice by typing in conda activate env_name

### 12.	Get and check the allocated socket by using the below command:

`echo $(ip a | grep -v -e "127.0.0.1" -e "inet6" | grep "inet" | awk {'print($2)}' | sed 's/\/.*//')
`
<br>
<br>
![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/15b14a38-bf68-433a-91e2-1b21388e2081)
<br>

### 13.	Note down the last 2 digits of the ip address.

### 14.	To activate Jupyter Lab use the following command:
`jupyter-lab --ip 10.10.10.X  (Where X is the last two digits that you observed before in Step13)
`
<br>
<br>
![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/eb8e29e5-1ded-4682-9887-3d8acd9dea9f)
<br>

### 15.	Open a fresh Powershell Instance and type ssh myidc -L 8888:10.10.10.X:8888 (Where X is the last two digits that you observed before in Step13)

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/58526019-dcdf-4834-9460-2c8ad5a5ab49)
<br>

### 16.	Open a local browser and type the following in the address bar: http://localhost:8888/lab

![image](https://github.com/shriramkv/SYCLwithIDC/assets/72274851/6b16edd6-3414-4d55-aa25-bfac6f800301)
<br>

### 17.	In the preceding screen you will be asked for a token. This can be found in the first powershell instance on the 6th last line.

</details>

# About the Libraries

## 1. oneDAL (oneAPI Data Analytics Library) <img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/bbaa57c5-ae31-4a84-a988-8482b85b5efe" height="60" width="60"><br>

The oneDAL.ipynb code file showcases the capabilities of the oneDAL library, which provides efficient data analysis and machine learning algorithms for a variety of use cases. Whether you're working on data preprocessing, linear algebra, statistical analysis, or machine learning tasks, oneDAL has you covered.
<details>
  <summary><h2>More about it</h2><img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/6120f1fb-dfec-473a-a067-23d2481066c2" height="60" width="60"></summary>

  #### :rocket: Jupyter startup guide
You can use python notebooks with the help of Jupyter* notebook to run the following files:

```bash
conda install -c conda-forge notebook scikit-learn-intelex
```  
or  
```bash
pip install notebook scikit-learn-intelex
```  
Run Jupyter after installation:
```bash
jupyter notebook --notebook-dir=./ --ip=* --no-browser
```  

#### :pencil: Examples of oneDAL


| Algorithm               | Workload       | Task            | Notebook       | Scikit-learn estimator|
| :----------------------:| :------------: | :---------------:| :------------: | :-------------------:|
|    LogisticRegression  |    CIFAR-100    |    Сlassification    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/logistictic_regression_cifar.ipynb)    | [sklearn.linear_model.LogisticRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html) |
|          SVC           |     Adult       |    Сlassification    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/svc_adult.ipynb) | [sklearn.svm.SVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html) |
| KNeighborsClassifier   |       MNIST     |    Сlassification    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/knn_mnist.ipynb) |    [sklearn.neighbors.KNeighborsClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html) |
|        NuSVR           | Medical charges |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/nusvr_medical_charges.ipynb) | [sklearn.svm.NuSVR](https://scikit-learn.org/stable/modules/generated/sklearn.svm.NuSVR.html) |
| RandomForestRegressor  |     Yolanda     |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/random_forest_yolanda.ipynb) | [sklearn.ensemble.RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) |
|        Ridge           | Airlines DepDelay |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/ridge_regression.ipynb) | [sklearn.linear_model.Ridge](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html) |
| ElasticNet  |    Airlines DepDelay     |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/ElasticNet.ipynb) | [sklearn.linear_model.ElasticNet](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html) |
|        Lasso           | YearPredictionMSD |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/lasso_regression.ipynb) | [sklearn.linear_model.Lasso](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html) |
| Linear Regression  |    YearPredictionMSD     |    Regression    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/linear_regression.ipynb) | [sklearn.linear_model.LinearRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) |
|        KMeans           | Spoken arabic digit |    Clustering    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/kmeans.ipynb) | [sklearn.cluster.KMeans](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) |
| DBSCAN  |     Spoken arabic digit     |    Clustering    | [View source on GitHub](https://github.com/intel/scikit-learn-intelex/blob/master/examples/notebooks/dbscan.ipynb) | [sklearn.cluster.DBSCAN](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html) |

![graph](https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/5d292ebb-ec6a-4870-88f5-b7ec993bcb59)

#### :pencil: Projects of oneDAL

| Algorithm               | Notebook       |
| :----------------------:| :------------: | 
|    Crop Prediction  |  [View source on GitHub](https://github.com/JoelJJoseph/CROP_PREDICTION_oneAPI)    | 
|    Heart Attack          |   [View source on GitHub](https://github.com/AkshayRamakrishnann/heartattack) | 


</details>



## 2. oneDNN (oneAPI Deep Neural Network Library) <img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/6395c82a-a490-4a2b-916e-77945c8142de" height="60" width="60"><br>

In the oneDNN.ipynb code file, you'll find examples that leverage the oneDNN library, designed to accelerate deep learning workloads. This library offers optimized primitives for convolutional neural networks (CNNs), recurrent neural networks (RNNs), and other deep learning models, enhancing both training and inference performance.

<details>
  <summary><h2>More about it</h2><img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/6120f1fb-dfec-473a-a067-23d2481066c2" height="60" width="60"></summary>

<img src="https://www.intel.com/content/dam/www/central-libraries/us/en/images/2022-07/onednn-stack-diagram-07jul22-rwd.png.rendition.intel.web.864.486.png">

# oneDNN Tutorials

| Type      | Name                 | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| Component | [getting_started](tutorial_getting_started.ipynb)  | The sample also includes a Jupyter notebook with step by step instructions on building code with different compilers and runtime configurations oneDNN support. |
| Component | [verbose_jitdump](tutorial_verbose_jitdump.ipynb) | This Jupyter Notebook demonstrates how to use Verbose Mode and JIT Dump to profile oneDNN samples. |
| Component | [analyze_isa_with_dispatcher_control](tutorial_analyze_isa_with_dispatcher_control.ipynb) | This Jupyter Notebook demonstrates how to use CPU Dispatch Control to generate JIT codes among different ISA on CPU and also analyze JIT kernels among ISAs.|
| Component | [Intel® VTune™ Profiler](tutorial_vtune_profiling.ipynb) | This Jupyter Notebook demonstrates how to use VTune™ Profiler to profile oneDNN samples and find out performance bottlenecks. |
| Component | [benchdnn_tutorial](benchdnn_tutorial.ipynb) | This Jupyter Notebook demonstrates how to use the benchDNN tool to validate and test oneDNN primitive executions |
>  Notice : Please use Intel® oneAPI DevCloud as the environment for jupyter notebook samples. \
Users can refer to [DevCloud Getting Started](https://devcloud.intel.com/oneapi/get-started/) for using DevCloud \
Users can use JupyterLab from DevCloud via "One-click Login in", and download samples via "git clone" or the "oneapi-cli" tool \
Once users are in the JupyterLab with downloaded jupyter notebook samples, they can start following the steps without further installation needed.

![graph](https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/353b9d93-2f18-41b9-856b-23d34b1ed3b0)

#### :pencil: Projects of oneDAL

| Algorithm               | Notebook       |
| :----------------------:| :------------: | 
|    Sign-Language  |  [View source on GitHub](https://github.com/JoelJJoseph/Sign-Language_oneApi)    | 
|    Breastcancer         |   [View source on GitHub](https://github.com/AkshayRamakrishnann/Breastcancer_oneDNN_Conv1D) | 


</details>

## 3. XGBoost with oneAPI  <img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/3c93722d-d90f-43f2-a03a-a04226e45e36" height="60" width="60"><br>

The XGB.ipynb code file demonstrates how to integrate the XGBoost library with oneAPI, leveraging the power of oneAPI's hardware acceleration. XGBoost is a popular machine-learning library for gradient boosting on decision trees, and when combined with oneAPI's optimizations, it becomes even more efficient and powerful.

<details>
  <summary><h2>More about it</h2><img src="https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/6120f1fb-dfec-473a-a067-23d2481066c2" height="60" width="60"></summary>
  
<img src=https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/7994fa5b-8e19-4f9b-960b-e572929fbad0>

<img src=https://github.com/shriramkv/MLwithoneAPI_IDC/assets/72274851/ecadf547-de84-4109-bd81-573115864918>

<br>**Key Takeaways**
- Intel optimizations available in XGBoost 1.4.3 offers prediction time speed-up ranging between 2.14x and 2.22x  compared to stock XGBoost 0.81 with XGBoost model trained with tuned hyperparameters on this dataset
- Intel optimizations available in daal4py offers additional  prediction time speed-up, overall ranging between 2.94x to 3.75x compared to stock XGBoost 0.81 with XGBoost model trained with tuned hyperparameters on this dataset

> No accuracy drop observed with the daal4py prediction

#### :pencil: Projects of XGBoost with oneAPI

| Algorithm               | Notebook       |
| :----------------------:| :------------: | 
|    CROP PREDICTION  |  [View source on GitHub](https://github.com/JoelJJoseph/CROP_PREDICTION_oneAPI)    | 
|    Fake Currency Detection        |   [View source on GitHub](https://github.com/JoelJJoseph/Fake-Currency-Detection-using-AI-ML) | 


</details>

# Getting Started

## To access and utilize the code examples provided in this repository, follow these steps:

⭐ Clone the repository to your local machine using the following command:

⭐ `git clone https://github.com/shriramkv/MLwithoneAPI_IDC.git`

⭐ Explore the individual code files (oneDAL.ipynb, oneDNN.ipynb, and XGB.ipynb) to understand how each library is used and optimized.

⭐ Refer to the attached documents for detailed documentation on each library and instructions for creating an Intel Developer Cloud (IDC) account to access additional resources.

## Contributions
We welcome contributions to this repository! If you've developed additional optimized code examples using Intel oneAPI libraries or want to improve existing code, feel free to submit pull requests.

Happy coding and optimizing with Intel's oneAPI toolkit! If you have any questions or need assistance, please don't hesitate to reach out.
