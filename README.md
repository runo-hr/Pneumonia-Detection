# Pneumonia-Detection  

## Objective
Train a deep learning model to classify Chest X-rays as either Pneumonia or Normal. Deploy the model on a web application.   

<blockquote>Status: Developing the web application. <a href='https://github.com/runo-hr/Flask'> Flask Web App </a> </blockquote>  

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
