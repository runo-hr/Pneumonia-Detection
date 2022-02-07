# Pneumonia-Detection  
<blockquote>
  README not complete. I will update soon.
  </blockquote>

## Overview
In this project, <a href='https://github.com/MargaretKagwiria'> Margaret Kagwiria </a> and I apply the Data Science Methodology in classifying
chest X-rays as either Normal or belomging to a Pneumonia patient.  

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


## Tech Stack  
1. Tensorflow  
2. Keras  
3. Flask  
4. Python  

## Approach  
Use transfer learning to fine tune Keras MobileNet and VGG16 models.  

Deploy trained model on a flask web application. (In this case, a personal portfolio web application)  

### Dataset  
<a href='https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia '> Chest X-Ray Images (Pneumonia) </a>  

This Dataset has a total of 5856 images - 1583 Normal images, 4273 Pneumonia images.  
The models were trained on two variations of the dataset.  
<ol>
  <li> Unbalanced Dataset (Half the full dataset) </li>
  <p> 
    Pneumonia:
      <ul>
        <li> 1282 Train </li>
        <li> 641  Validation </li>
        <li> 158  Test</li>
       </ul>
    Normal:
      <ul>
        <li> 475 Train </li>
        <li> 238 Validation </li>
        <li> 158 Test</li>
      </ul>
  </p>
   
  <li> Balanced Dataset  </li>
  <p> 
    Pneumonia:
      <ul>
        <li> 950  Train </li>
        <li> 475  Validation </li>
        <li> 158  Test</li>
       </ul>
    Normal:
      <ul>
        <li> 950 Train </li>
        <li> 475 Validation </li>
        <li> 158 Test</li>
      </ul>
  </p>
</ol>

To organize the dataset use the files in the Organize Dataset directory at the top of this repository.  

