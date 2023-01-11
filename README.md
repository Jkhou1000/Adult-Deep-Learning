# Deep Learning Prediction using Tensorflow and Keras

## Data 
This project uses [data provided by the UCI](https://archive.ics.uci.edu/ml/datasets/Adult), a census on people and their income, specifically things like ones education, age, sex, if they earn over or under 50k. Using this data I trained a Deep Learning model to predict the income of a person with 14 attributes (not counting the target variable)

1. income  (The target) <=50k or >50k
2. age: continuous.
3. workclass: Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
4. fnlwgt: continuous.
5. education: Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
6. education-num: continuous.
7. marital-status: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
8. occupation: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
9. relationship: Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
10. race: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
11. sex: Female, Male.
12. capital-gain: continuous.
13. capital-loss: continuous.
14. hours-per-week: continuous.
15. native-country: United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.

## Data Viz
 ![830df649-ca47-4a49-ada4-68d4882bf677](https://user-images.githubusercontent.com/105755535/211839375-93cf4f0c-2129-45dd-a49e-0d6ecec44a86.png)
 
The Boxen plot details the age most people are seperated by income and gender. A large chunk of people both male and female that earn under 50k are from an age range of around 27-45, women skewing a little younger with their first quartile at around 25. Barring a couple of outliers, the maximum age for men taking this census do not go over age 85 while for women it maxes out around 73(not including the outliers of course).
 
![9b887363-2ca4-44e6-8d26-5261ef3ddb64](https://user-images.githubusercontent.com/105755535/211839422-003ddb7c-41e0-4caf-b2a7-b4678a93955c.png)

Income based on education gives us a look into how many people have had a education and the income they earn. note that this is a vague correlation and does not necessarily tie into whatever job they may have, as notably a lot of people who have completed college still have lower incomes, outweighing those who do earn >50k. The only educations where more people earn >50k are those who have done prof-school, a masters degree, or have a doctorate. The majority of the people have at least finished Highschool, and of course earn <=50k, on the other end of the spectrum, an extreme minority have only preschool education and only earn <=50k. 


## Metrics
As a classification task, this Neural Network was tuned for accuracy, the overall performance of which is summed up by the f1-score. 3 models were made, and the final one was the best one of the 3, earning a modest .70 (about 70% of the data is predicted correctly). The training and testing loss showed signs of overfitting, which I was able to alleviate somewhat through the final model. The changes were small however, and ultimately much more can be done to improve it further.

### Model Loss & Accuracy
![Model Loss](https://user-images.githubusercontent.com/105755535/211419795-4cc203ce-ed36-42b5-9cbd-adc4d4027025.png)
![Model Accuracy](https://user-images.githubusercontent.com/105755535/211419833-1519622a-bc4f-4fa4-94df-836e5d8074fe.png)

The loss does slightly decrease over time for testing but the accuracy still fluctuates in the testing. The training data is fine of course but it is preferable that it performs well on testing, or both of course.

### Confusion Matrices
![Training adult](https://user-images.githubusercontent.com/105755535/211420765-ad3dcd15-e327-4a4e-94b1-0f14205445c2.png)

Training Evaluation:

              precision    recall  f1-score   support

       <=50k       0.90      0.91      0.90     18506
        >50k       0.70      0.70      0.70      5914
        
        accuracy                       0.85     24420
       macro avg   0.80      0.80      0.80     24420
     weighted avg  0.85      0.85      0.85     24420

![Testing Adult](https://user-images.githubusercontent.com/105755535/211420792-1347c419-e7d4-47bd-91b0-d2207ef237b4.png)

Testing Evaluation:

              precision    recall  f1-score   support

       <=50k       0.91      0.91      0.91      6214
        >50k       0.71      0.70      0.70      1927
        
        accuracy                       0.86      8141
       macro avg   0.81      0.80      0.81      8141
    weighted avg   0.86      0.86      0.86      8141

The one thing the training and testing predictions had in common were the performances on the true positives, namely its ability to predict people who earn over 50k. This may be due to the fact that there are less people who earn over 50k, which means there is less data for it to train on, as well as the fact that there aren't that many common trends in the data for earners over 50k.

### Next Steps
Further improvements are definitely needed, training it on less data to avoid overfitting, tinkering with Dropout and regularization more. Using different types of layers may also yield more substantial changes as well. 

## Citations and Contact
This data was of course obtained from the UCI Machine Learning respoitory

*Ronny Kohavi and Barry Becker
Data Mining and Visualization
Silicon Graphics.
e-mail: ronnyk '@' live.com for questions.

If you have any questions please contact me at Jkhoury10000@gmail.com

