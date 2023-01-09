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
 
## Metrics
As a classification task, this Neural Network was tuned for accuracy, the overall performance of which is summed up by the f1-score. I ran through 3 models, and the final one was the best one of the 3, earning a modest .70 (about 70% of the data is predicted correctly). The training and testing loss showed signs of overfitting, which I was able to alleviate somewhat through the final model. The changes were small however, and ultimately much more can be done to improve it further:
### Model Loss & Accuracy
![Model Loss](https://user-images.githubusercontent.com/105755535/211419795-4cc203ce-ed36-42b5-9cbd-adc4d4027025.png)
![Model Accuracy](https://user-images.githubusercontent.com/105755535/211419833-1519622a-bc4f-4fa4-94df-836e5d8074fe.png)
The loss does slightly decrease over time for testing but the accuracy still fluctuates.
## Confusion Matrices
![Training adult](https://user-images.githubusercontent.com/105755535/211420765-ad3dcd15-e327-4a4e-94b1-0f14205445c2.png)
![Testing Adult](https://user-images.githubusercontent.com/105755535/211420792-1347c419-e7d4-47bd-91b0-d2207ef237b4.png)
The one thing the training and testing predictions had in common were the performances on the true positives, namely its ability to predict people who earn over 50k. This may be due in part
