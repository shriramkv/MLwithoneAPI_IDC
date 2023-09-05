# Intel oneAPI Optimized Code Examples Repository

Welcome to the Intel oneAPI Optimized Code Examples Repository! This repository contains optimized code examples that utilize various libraries from Intel's oneAPI toolkit. The three code files included in this repository demonstrate the usage of the following libraries:

oneDAL (oneAPI Data Analytics Library) - oneDAL.ipynb
oneDNN (oneAPI Deep Neural Network Library) - oneDNN.ipynb
XGBoost with oneAPI - XGB.ipynb

## Intel Developer Cloud 
To gain access to a wealth of resources, discussions, and support related to Intel's oneAPI toolkit, you can create an Intel Developer Zone (IDZ) account using the attached documents:
Creating an IDC Account Guide: https://www.youtube.com/watch?v=PhzlMQ8-GE4&t=696s
Step by Step Guidelines for setting up the IDC and to launch the Jupyter Notebook.

1.	Generate an ssh key using the command ssh-keygen in the power shell as an administrator. 

2.	Open the generated key file using notepad and copy the contents of the file.(C:\Users\<<username>>\.ssh is the path - file name is id_rsa.pub, use the command notepad id_rsa.pub) 

3.	Nextly login or register into the Developer Cloud and add the key under the profile section. https://scheduler.cloud.intel.com/

4.	Open .ssh folder and create a config file with the below commands:
Host myidc
Hostname idcbetabatch.eglb.intel.com
User uXXXXXX #← Request "scheduled access" at https://scheduler.cloud.intel.com/#/systems" to get your user identifier.
IdentityFile ~/.ssh/id_rsa
#ProxyCommand ncat --proxy YourProxy:XXXX %h %p --proxy-type socks5 %h %p  ## Uncomment if necessary
ServerAliveInterval 60
ServerAliveCountMax 10
StrictHostKeyChecking no 
UserKnownHostsFile=/dev/null

5.	On Powershell type ssh myidc to connect to your head node instance. This will enable you to be authenticated. 

6.	Next to connect to an interactive node type in the below command:
srun --pty bash
source /opt/intel/oneapi/setvars.sh
This will get the batch node activated! You will see this clearly in the powershell terminal. u***@idc-beta-batch-head-node would get changed to u***@idc-beta-batch-pvc-node
7.	Configure your shell using the command conda init bash

8.	Close the existing instance to make sure that the configuration changes reflect using the command exit
9.	You are taken back to the head node again, connect to the interactive node again by repeating Step6 again.

10.	To check the available environments type in the command conda env list

11.	Choose the environment of your choice by typing in conda activate env_name

12.	Get and check the allocated socket by using the below command:
echo $(ip a | grep -v -e "127.0.0.1" -e "inet6" | grep "inet" | awk {'print($2)}' | sed 's/\/.*//')

13.	Note down the last 2 digits of the ip address.

14.	To activate Jupyter Lab use the following command:
jupyter-lab --ip 10.10.10.X  (Where X is the last two digits that you observed before in Step13)

15.	Open a fresh Powershell Instance and type ssh myidc -L 8888:10.10.10.X:8888 (Where X is the last two digits that you observed before in Step13)

16.	Open a local browser and type the following in the address bar: http://localhost:8888/lab

17.	In the preceding screen you will be asked for a token. This can be found in the first powershell instance on the 6th last line.

## About the Libraries

1. oneDAL (oneAPI Data Analytics Library)
The oneDAL.ipynb code file showcases the capabilities of the oneDAL library, which provides efficient data analysis and machine learning algorithms for a variety of use cases. Whether you're working on data preprocessing, linear algebra, statistical analysis, or machine learning tasks, oneDAL has you covered.

2. oneDNN (oneAPI Deep Neural Network Library)
In the oneDNN.ipynb code file, you'll find examples that leverage the oneDNN library, designed to accelerate deep learning workloads. This library offers optimized primitives for convolutional neural networks (CNNs), recurrent neural networks (RNNs), and other deep learning models, enhancing both training and inference performance.

3. XGBoost with oneAPI
The XGB.ipynb code file demonstrates how to integrate the XGBoost library with oneAPI, leveraging the power of oneAPI's hardware acceleration. XGBoost is a popular machine learning library for gradient boosting on decision trees, and when combined with oneAPI's optimizations, it becomes even more efficient and powerful.

## Getting Started

To access and utilize the code examples provided in this repository, follow these steps:

Clone the repository to your local machine using the following command:

git clone https://github.com/your-username/your-repo-name.git

Explore the individual code files (oneDAL.ipynb, oneDNN.ipynb, and XGB.ipynb) to understand how each library is used and optimized.

Refer to the attached documents for detailed documentation on each library and instructions for creating an Intel Developer cloud (IDC) account to access additional resources.

## Contributions
We welcome contributions to this repository! If you've developed additional optimized code examples using Intel oneAPI libraries or want to improve existing code, feel free to submit pull requests.

Happy coding and optimizing with Intel's oneAPI toolkit! If you have any questions or need assistance, please don't hesitate to reach out.
