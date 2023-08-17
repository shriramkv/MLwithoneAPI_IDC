# Fetal Health Prediction using oneDAL Classification Algorithms
# This project is a machine learning application that predicts the health status of a fetus using three different classification algorithms: logistic regression, SVM, and KNN. The project uses the oneDAL library from Intel to implement the classification algorithms.
![shutterstock_133423673](https://user-images.githubusercontent.com/111365771/221896792-e607c68e-df17-424b-b373-810a087dd9e5.jpg)

# Dataset
The dataset used for this project is the Fetal Health Classification Dataset from Kaggle. The dataset contains 21 features and a binary target variable indicating whether the fetal health is normal or not. The dataset is split into training and testing sets using a 70-30 split.

# Classification Algorithms
The three classification algorithms used in this project are:
## Logistic Regression
![download (1)](https://user-images.githubusercontent.com/111365771/221899799-1c8ab492-23ac-411a-bfea-af531ecf6045.png)

A linear classification algorithm that models the probability of the target variable using a logistic function. The model is trained by minimizing the cross-entropy loss between the predicted probabilities and the true labels.
## Support Vector Machine

![download (2)](https://user-images.githubusercontent.com/111365771/221900192-a698d3f8-c17a-4039-b9f8-caa8fce94c26.png)

A non-linear classification algorithm that finds the best hyperplane to separate the data into different classes. The hyperplane is chosen to maximize the margin between the classes. The model is trained by solving a convex optimization problem.
## K-Nearest Neighbour
![0_ItVKiyx2F3ZU8zV5](https://user-images.githubusercontent.com/111365771/221900664-25f10184-a0a5-4580-ac58-b567d164228d.png)

A non-parametric classification algorithm that predicts the class of a new data point based on the classes of its K nearest neighbors in the training data. The model is trained by storing the training data and computing the distances between data points.

# Installation

To run this project, you will need to have Python 3 and the following packages installed:

->pandas

->numpy

->scikit-learn

->oneDAL

# Intel DevMesh
This project was implemented using the oneDAL library from Intel DevMesh. oneDAL is an open-source library that provides optimized implementations of common machine learning algorithms for CPUs and GPUs. The library is written in C++ and provides Python bindings for easy integration into Python-based machine learning applications.

# Results

The performance of the three classification algorithms on the testing data is as follows:

->Logistic Regression: 90.14% accuracy

->SVM: 80.75% accuracy

->KNN: 77.94% accuracy
As we can see, logistic regression performs the best, with an accuracy of over 90%, while SVM and KNN perform worse, with accuracies of around 80% and 77%, respectively.
