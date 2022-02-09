# Pneumonia-Detection  
<blockquote>
  README not complete. I will update soon.
  </blockquote>

## Overview
In this project, <a href='https://github.com/MargaretKagwiria'> Margaret Kagwiria </a> and I apply the Data Science Methodology in classifying
chest X-rays as either Normal or belomging to a Pneumonia patient.  

## Tech Stack  
1. Tensorflow  
2. Keras  
3. Flask  
4. Python 

## Data Science Methodologies  
For this project, we applied the <b>Foundational Methodology</b> for Data Science by John Rollins. However, it is not the only methodology in data science.  
In data mining, the <b>Cross Industry Process for Data Mining (CRISP-DM)</b> methodology is widely used.   
We will first get an overview of CRISP-DM and later on cover the Foundational Methodology with reference to this project.  

### Cross Industry Process for Data Mining (CRISP-DM)  
This process is aimed at increasing the use of data mining over a wide variety of business applications and industries.  
The intent is to take case specific scenarios and general behaviors to make them domain neutral.  
#### Steps


![CRISP-DM](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0103EN-SkillsNetwork/labs/Module%201/images/DS_3.1.0.5-CRISP-DM-Model-2.png)  

1. <b>Business Understanding : </b>Intention of the project is established
2. <b>Data Understanding : </b> Data is collected. This stage relies on the business understanding.  
3. <b>Data Preparation : </b>Data is transformed into a useable subset unless it is determined that more data is needed. The chosen dataset is checked for questionable, missing or ambiguous cases.  
4. <b>Modelling : </b>Models are used to reveal useful insights in the data. Models reveal patterns and structures within the data. Models are trained on a portion of the data and necessary adjustments made.
5. <b>Evaluation : </b>The model is tested on new data not included in the trainig set but part of the dataset.
6. <b>Deployment : </b> The model is used on new data outside the scope of the dataset and by new stakeholders. This stage might reveal new variables and needs for the model and dataset. These could lead to revisions of either business needs and actions, or the model and data, or both.  

### Foundational Methodology  
#### Steps  


![foundational-methodology](methodology.jpeg)  

The methodology aims to answer the following questions.  
#### From problem to approach  
1. <b>What is the problem that you are trying to solve? </b>  
Classify chest x-rays as either Normal of of a patient infected with Pneumonia.  

2.  <b>How can you use data to answer the question? </b>  
Use transfer learning to fine tune Keras MobileNet and VGG16 models to a dataset of chest x-ray images. 

#### Working with the data
3.  <b>What data do you need to answer the question </b>  
Chest x-ray dataset with two categories; Normal and Pneumonia  

4.  <b>Where is the data coming from (identify all sources) and how will you get it? </b>  
Datasets can be found by either manually searching specific sites or by scraping different sources on the web.  
A manual search is okay where datasets are readily available.  
When the data required is not readily available, building a web scraper might be necessary.
We used the manual search and found the following datasets:  
    <ul>  
      <li>
      <a href='https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia '> Chest X-Ray images (Pneumonia) | Paul Mooney </a> We chose this dataset. 
      </li>
      <li>
      <a href='https://www.kaggle.com/pcbreviglieri/pneumonia-xray-images '> Pneumonia X-Ray images | Paulo Breviglleri </a> Adaptation of Paul Mooney's Chest X-Ray.
      </li>    
      <li>
      <a href='https://www.kaggle.com/andrewmvd/pediatric-pneumonia-chest-xray'> Paediatric Pneumonia Chest X-Rays </a> 
      </li>
      <li> 
      <a href='https://www.kaggle.com/prashant268/chest-xray-covid19-pneumonia'> Chest x-rays COVID-19 and Pneumonia  </a> This has 3 categories; COVID-19, Pneumonia and Normal.  
      </li>
      <li>
      <a href='https://www.kaggle.com/jtiptj/chest-xray-pneumoniacovid19tuberculosis'> Chest x-rays COVID-19, Tuberculosis and Pneumonia  </a>  
      </li>
      <li>
      <a href='https://www.kaggle.com/balnyaupane/pneumonia-chest-xray-dataset-200-by-200-image'> Pneumonia_Chest _X-ray_Image_Dataset  </a>
      </li>
    </ul>

5. <b> Is the data collected representative of the problem to be solved?</b>  
Yes. The data has images categorized into NORMAL and PNEUMONIA.  

6. <b> What additional work is required to manipulate and work with the data?</b>  
We redistributed the amount of observations for training and validation purposes to allow for a more balanced machine learning exercise.  
This Dataset has a total of 5856 images - 1583 Normal images, 4273 Pneumonia images.  
The models were trained on two variations of the dataset - Unbalanced and Balanced.    
[Redistribute-images](/Organize_Dataset/organize_data.ipynb) creates the variations.  
We also preprocessed the images as required to pass them to VGG16 and MobileNet models. This preproccessing step can be found here [mobilenet](/MobileNet/mobilenet.ipynb) and [vgg16](/VGG16/VGG16.ipynb)

#### Deriving the answer  
7. <b>In what way can the data be visualized to get to the answer that is required?</b>  

    When transfer learning, one the main goals is to find the optimum number of layers to retrain so as to get get the most efficient model.  

    Evaluation metrics for model efficacy are dependent on the dataset and desired results.  
    One of the datasets we used for this exercise has imbalanced classes. We needed to compare the performance of a model trained on an imbalanced dataset with that trained on a balanced dataset.

    As such, we chose F1-score as the evaluation metric. We did evaluate on accuracy, precision and recall but went with the F-score and here is why.  

    <b>Accuracy</b>   
    <ul>
      <li>Only good when you have balanced classes</li>   
      <li>accuracy = correct predictictions / all predictions</li>  
      a = (tp +tn)/(tp +tn +fp +fn)
    </ul>

    <b>Precision</b> 
    <ul>
      <li>Higher precision >> less false positives.</li>   
      <li>precision = true positives / predicted positives</li>  
      p = tp / (tp + fp)
    </ul>

    <b>Recall</b>
    <ul>
      <li>Higher recall >> less false negatives.</li>   
      <li>recall = true positives / actual positives</li>  
      p = tp / (tp + fn)
    </ul>  

    <b>F1-score</b>
    <ul>
      <li>Ttadeoff of recall and precision</li>   
      <li>f1_score = 2 *(precision_score * recall_score)/ (precision_score + recall_score)</li>  
    </ul>   


    So, how to visualize?  

    We trained a number of model variations on each of the datasets and made plots of F-scores against number of layers retrained.  
    
    Here are the results.  

    <b>VGG16 | Models trained on a balanced dataset vs Unbalanced dataset</b>

    ![f-scores](/VGG16/images/f_scores.png)  

    <b>MobileNet | Evaluation metrics of Models Trained on Unbalanced Dataset</b>  

    ![eval-metrics](/MobileNet/images/evaluation_unbalanced.png)  

    <b>MobileNet | False Predictions against layers retrained </b>

    ![false-preds](/MobileNet/images/false_preds_test.png)  

    [view-false-predictions-data](/MobileNet/evaluation/test_results.xlsx)  

    <em> Which model to choose? </em>  
    Ideally we want a model that classifes all images in the test set. However, the models gives wrong predictions for some images.  
    Different models give a different number of false positives and false negatives.  
    Below is a filter of models with both false predictions false than or equal 4.  

    ![false-preds-filter-4](/MobileNet/images/false_preds_filter_4.png)  

    These models also have high f-scores. However its important to note that there are some models with  higher f-scores but are left out due to our filtration criteria.  
    [Here](/MobileNet/evaluation/false_preds_fscore.csv) is a csv file of all the models, their false predictions and f-scores.






 



