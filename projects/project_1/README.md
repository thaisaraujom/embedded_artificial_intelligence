# Model Card

Model cards are a succinct approach for documenting the creation, use, and shortcomings of a model. The idea is to write a documentation such that a non-expert can understand the model card's contents. For additional information see the Model Card paper: https://arxiv.org/pdf/1810.03993.pdf

## Model Details
Thaís Medeiros created the model. A complete data pipeline was built using Google Colab, Scikit-Learn, TensorFlow and Weights & Bias to train KNN, CNN and MLP models. The big-picture of the data pipeline is shown below:

<img width="800" src="img/workflow.png">

## Intended Use
This model is used as a proof of concept for the evaluation of an entire data pipeline incorporating Machine Learning fundamentals. The data pipeline is composed of the following stages: a) ``fecht data``, b) ``preprocess``, c) <s>``check data``</s>, d) ``segregate``, e) ``train`` and f) ``test``.

## Training Data

The purpose of this dataset is to correctly classify an image as containing a dog, cat, or panda. Containing only 3,000 images, the Animals dataset is meant to be another **introductory** dataset
that we can quickly train a KNN, CNN or MLP model and obtain initial results that has potential to be used as a baseline. 

After the EDA stage of the data pipeline, it was noted that the images in training data has different resolutions. A pre-processing stage is necessary in order to normalize all images using the same size. 

<img width="600" src="img/EDA.png">


## Evaluation Data
The dataset under study is split into Train and Test during the ``Segregate`` stage of the data pipeline. 75% of the clean data is used to Train and the remaining 25% to Test. 
For hyperparameter tuning, 25% of Train is used to Validation.

## Metrics
In order to follow the performance of machine learning experiments, the project marked certains stage outputs of the data pipeline as metrics. The metrics adopted are: [accuracy](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html), [f1](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html#sklearn.metrics.f1_score), [precision](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html#sklearn.metrics.precision_score), [recall](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html#sklearn.metrics.recall_score).

To calculate the evaluations metrics is only necessary to run:

The follow results will be shown:

**Model** | **Stage [Run]**                        | **Accuracy** | **F1** | **Precision** | **Recall** | 
--------------|------------------|--------------|--------|---------------|------------|
KNN |Test [grateful-pine-6](https://wandb.ai/thaisaraujom/first_image_classifier/runs/239kkt4e?workspace=user-thaisaraujom) | 0.4693 | 0.4737  | 0.5419         | 0.4693     |  
MLP |Test [graceful-monkey-8](https://wandb.ai/thaisaraujom/first_image_classifier/runs/2dfr2sn2?workspace=user-thaisaraujom) | 0.576 | 0.5817  | 0.5927         | 0.576     |  
CNN |Test [curious-sunset-15](https://wandb.ai/thaisaraujom/cnn_classifier/runs/f85bc2vk?workspace=user-thaisaraujom) | 0.6667 | 0.664  | 0.662      | 0.6667     |  

## Ethical Considerations

We may be tempted to claim that this dataset contains the only attributes capable of predicting if there is a cat, dog or a panda in an image. However, this is not the case. The dataset is composed of 3,000 images, which is a small number of images to train a model. The dataset is also composed of images with different resolutions, which may lead to a model that is not robust to different image sizes.

## Caveats and Recommendations
It should be noted that the model trained in this project was used only for validation of a complete data pipeline. It is notary that some important issues related to size of images exist, and adequate techniques need to be adopted in order to balance it. Including data augmentation techniques, for example.

## How to run
1. Create an account on [Wandb platform](https://wandb.ai/)

2. Clone this repository
```
git clone https://github.com/thaisaraujo2000/embedded_artificial_intelligence.git
```
3. Import to [Google Colab](https://colab.research.google.com/) the files

4. Change the username or team name where you're sending runs

5. Run the files inside each folder in ascending order, according to numbering

## Reference
[Ivanovitch's Repository](https://github.com/ivanovitchm/embedded.ai)
