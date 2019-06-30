# Project Plagiarism Detection

This project relate to building a plagiarism detector that examines a text file and performs binary classification; labeling that file as either *plagiarized* or *not*, depending on how similar that text file is to a provided source text. Detecting plagiarism is an active area of research; the task is non-trivial and the differences between paraphrased answers and original work are often not so obvious..

## Getting Started

### General Outline

This project will be broken down into three main notebooks:

**Notebook 1: Data Exploration**
* Load in the corpus of plagiarism text data.
* Explore the existing data features and the data distribution.
* This first notebook is **not** required in your final project submission.

**Notebook 2: Feature Engineering**

* Clean and pre-process the text data.
* Define features for comparing the similarity of an answer text and a source text, and extract similarity features.
* Select "good" features, by analyzing the correlations between different features.
* Create train/test `.csv` files that hold the relevant features and class labels for train/test data points.

**Notebook 3: Train and Deploy Your Model in SageMaker**

* Upload your train/test feature data to S3.
* Define a binary classification model and a training script.
* Train your model and deploy it using SageMaker.
* Evaluate your deployed classifier.

### Prerequisites

The smallest GPU instance available when using SageMaker is the ml.t2.medium instance and it is perfectly adequate for completing the project.

## Running the tests

Once our model is deployed, we can see how it performs when applied to the test data.
Assuming data is stored locally in data_dir and named test.csv. The labels and features are extracted from the .csv file.

We use our deployed `predictor` to generate predicted, class labels for the test data. Then we Compare those to the *true* labels, `test_y`, and calculate the accuracy as a value between 0 and 1.0 that indicates the fraction of test data that our model classified.

### Break down into end to end tests

In this project we choosed two models LinearLearner which is a builtin sagemaker algorithm and PyTorch Neural Network Classifier. After that we compare and select the best one.

To implement a custom classifier, we'll need to complete a `train.py` script. we've been given folder `source_pytorch` which hold starting code for  PyTorch model, respectively. This directory has a `train.py` training script.

## Built With

* [Amazon SageMaker](https://aws.amazon.com/sagemaker/) - The web framework used
* [Amazon S3](https://aws.amazon.com/s3/) - The web storage used
* [Amazon API](https://aws.amazon.com/api-gateway/) - The API used

## Authors

* **Keyvan Tajbakhsh** - [keyvantaj](https://github.com/keyvantaj)

See also the list of [contributors](https://github.com/udacity/machine-learning/graphs/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
