# Evaluating the Robustness of Cloud Auto-AI Models against Adversarial Attacks

**Collaborators: Aashka Trivedi and Anya Trivedi**

This project aims to compare the performance of off-the-shelf Cloud Auto-AI services when exposed to adversarial examples. Various cloud providers such as IBM cloud or Google Cloud Platorm (GCP)house powerful ”Auto-AI” platforms that allow users to build world-class Machine Learning models without much ML expertise. In particular, we aim to see how robust these Auto-AI models are towards adversarial examples in the Image Classification domain, and perform a comparative study between the two cloud platforms’ models.

We aim to train Auto-AI models from the two cloud platforms to perform image classification on the MNIST-10 dataset (a hand-written digit recognition dataset with 10 classes). We then generate adversaries for the models for each dataset using the AdverTorch framework. We measure the percentage of mis-classified examples to gauge the robustness of the model.

## IBM Cloud

### Implementation Details

IBM Cloud's Auto-AI takes in CSV files as inputs, not images. We thus use the MNIST training and test data provided by PyTorch, which we save in csv format. This is done in the later half of the `AdversarialExampleGeneration.ipynb` notebook.

The best pipeline's notebook and the experiment notebook are saved in `ibmcloud_autoai/MNIST_p2.ipynb` and `ibmcloud_autoai/MNIST_experiment.ipynb` respectively.

### Observations

1. AutoAI picks the top 2 algorithm, and builds 4 pipelines (with different hyperparameters) with each algorithm
2. The best model is selected as Pipeline 2, which is an LGBM Classifier with "HPO-1" Optimization, which has an accuracy score of 0.898

## Adversarial Example Generation

To generate the adversarial examples, we follow [PyTorch's Tutorial](https://pytorch.org/tutorials/beginner/fgsm_tutorial.html) that uses FGSM to generate adversarial examples. We use epsilon values of 0.15 and 0.3 to conduct the attacks, whose code is in `AdversarialExampleGeneration.ipynb`.

## Useful Links

- [IBM Cloud AutoAI Tutorial](https://developer.ibm.com/tutorials/generate-machine-learning-model-pipelines-to-choose-the-best-model-for-your-problem-autoai/)
- [IBM Cloud AutoAI Code Generation](https://github.com/IBM/AutoAI-code-generation)
- [PyTorch Adversarial Attack Generation](https://pytorch.org/tutorials/beginner/fgsm_tutorial.html)
- [MNIST to CSV Conversion](https://pjreddie.com/projects/mnist-in-csv/)
- [AdverTorch](https://github.com/BorealisAI/advertorch)
