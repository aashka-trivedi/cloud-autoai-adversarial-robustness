# Evaluating the Robustness of Cloud Auto-AI Models against Adversarial Attacks

**Collaborators: Aashka Trivedi and Anya Trivedi**

This project aims to compare the performance of off-the-shelf Cloud Auto-AI services when exposed to adversarial examples. Various cloud providers such as IBM cloud or Google Cloud Platorm (GCP)house powerful ”Auto-AI” platforms that allow users to build world-class Machine Learning models without much ML expertise. In particular, we aim to see how robust these Auto-AI models are towards adversarial examples in the Image Classification domain, and perform a comparative study between the two cloud platforms’ models.

We aim to train Auto-AI models from the two cloud platforms to perform image classification on the MNIST-10 dataset (a hand-written digit recognition dataset with 10 classes). We then generate adversaries for the models for each dataset using the AdverTorch framework. We measure the percentage of mis-classified examples to gauge the robustness of the model.

## Implementation Details - IBM Cloud

IBM Cloud's Auto-AI takes in CSV files as inputs, not images. We thus use the MNIST training and test data provided by [Kaggle] (https://www.kaggle.com/oddrationale/mnist-in-csv) in csv format.
