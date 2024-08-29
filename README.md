# Asteroid Threat Classification

## Dataset

This dataset is from Kaggle and can be found [here](https://www.kaggle.com/shrushtijoshi/asteroid-impacts).

## Objectives

The main objective of this project is:
> Develop a system to detect asteroids that would threaten to life on Earth.

To achieve the main objective, here are sub-objectives:
1. Perform EDA (exploratory data analysis) of asteroid data.
2. Normalize data to equalize features' scales.
3. Develop supervised machine learning approach to classify asteroids as "threat" or "no threat".
4. Deploy model (if time permits)

## EDA Insights
- Data is heavily skewed towards False (No Threat) asteroids.
- None of the features exceed 0.25 correlation with Hazardous target.
- Observed hard distinction when comparing Asteroid Magnitude and Minimum Orbit Intersection Distace (AU) columns with hue on target variable.

## ML Approach Insights
- With all original columns, Decision tree produced 100% accuracy, precision and recall.
  - As previously observed, two features were directly determining the output to 100% accuracy: Asteroid Magnitude and Minimum Orbit Intersection Distace (AU). It is reasonable to conclude that a threshold was applied to these two columns to determine the target label.
  - *New approach: Remove Asteroid Magnitude and Minimum Orbit Intersection Distace (AU) columns and use the other features to predict Hazardous label. This removes possibility of deterministic results, which defeats the purpose of using an ML approach.*
  - Normalization did not improve the accuracy, precision, and recall of any of the models significantly.
  - Best overall performing model was Decision Tree, with the best combination of accuracy, precision, and recall (0.886, 0.454, and 0.259 respectively).

## Lessons
1. Data is everything. Using EDA to discover unique or unusual patterns in data before prediction is invaluable.
2. Analysis > ML. Performing analysis before modeling will save lot of time in the long run.
3. Be ready for unexpected results. Real-world data is messy. It is best to embrace this norm and act accordingly by trying different methods and seeing what fits the domain and business problem.
4. Accuracy is not always a good metric. In a skewed dataset like this, a high accuracy is a false indicator of good performance. Therefore, use other metrics that are protected against class imbalance, like precision, recall, F1 and more.
5. Don't underestimate simple models. My cecision tree was a simple model that revealed underlying biases in the data. And it was the best performing in the end as well. Therefore, don't discount the value that simple models can bring.
6. Be passionate and enjoy the journey. 

