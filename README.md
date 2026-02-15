# Lab 5: Face Detection and K-Means Clustering

## Aim
The objective of this assignment is to implement face detection using OpenCV and perform K-Means clustering on the detected faces based on their color features (Hue and Saturation) in the HSV color space. Additionally, the project aims to classify a template image (a new face) into one of the generated clusters.

## Methodology
1.  **Face Detection**: 
    - Used OpenCV's Haar Cascade classifier (`haarcascade_frontalface_default.xml`) to detect faces in the group image (`plaksha_Faculty.jpg`).
    - Rectangles were drawn around detected faces.

2.  **Feature Extraction**:
    - Converted the detected face regions from BGR to HSV color space.
    - Extracted the mean **Hue** and **Saturation** values for each face to use as features for clustering.

3.  **K-Means Clustering**:
    - Applied K-Means clustering (with $k=2$) on the extracted (Hue, Saturation) dataset to group faces based on skin tone/lighting features.
    - Visualized the clusters and their centroids on a 2D scatter plot.

4.  **Template matching/Classification**:
    - Processed a template image (`Dr_Shashi_Tharoor.jpg`) to detect the face and extract its HSV features.
    - Predicted the cluster label for the template face using the trained K-Means model.
    - Visualized the template face position relative to the existing clusters.

## Key Findings & Conclusion
- **Face Detection**: The Haar cascade successfully detected multiple faces in the faculty group photo.
- **Clustering**: The faces were separated into two distinct clusters based on color characteristics. The scatter plot highlights the separation between these groups.
- **Classification**: The template image was assigned to one of the clusters, demonstrating how simple color-based features can group similar facial images under specific lighting conditions.

## Report Q&A

#### 1. What are the common distance metrics used in distance-based classification algorithms? 

The common distance metrics include:
- **Euclidean Distance**: The straight-line distance between two points in n-dimensional space. It is the most widely used metric.
- **Manhattan Distance**: The sum of absolute differences between the coordinates of two points.
- **Minkowski Distance**: A generalized form of both Euclidean and Manhattan distance, parameterized by *p*.
- **Cosine Similarity / Distance**: Measures the cosine of the angle between two vectors; useful for high-dimensional text data.
- **Hamming Distance**: Counts the number of positions at which the corresponding symbols are different; commonly used for categorical or binary data.
- **Chebyshev Distance**: The maximum of the absolute differences between coordinates.
- **Mahalanobis Distance**: Accounts for correlations between features and is scale-invariant.

#### 2. What are some real-world applications of distance-based classification algorithms? 

- **Face recognition**: Classifying faces by comparing feature distances (as done in this lab).
- **Recommendation systems**: Finding similar users or items (collaborative filtering with KNN).
- **Medical diagnosis**: Classifying patients based on symptoms or biomarker similarity.
- **Handwriting / digit recognition**: Classifying handwritten characters by comparing pixel feature distances (e.g., MNIST dataset).


#### 3. Explain various distance metrics. 

a) **Euclidean Distance**: This is the most common way to measure distance, like measuring the straight-line distance between two points on a piece of paper with a ruler. It calculates the shortest path between point A and point B. It works well when all features are numeric and have similar scales.

b) **Manhattan Distance**: Imagine you are in a city with grid-like streets and you want to go from one intersection to another. You can't go through buildings, so you have to walk along the streets (horizontal + vertical distance). That sum of horizontal and vertical steps is the Manhattan distance. It is useful when your data has many dimensions or when outliers might mess up the Euclidean calculation.

c) **Minkowski Distance**: This is a generalized form that combines both Euclidean and Manhattan distances. It uses a parameter 'p'. If p=1, it becomes Manhattan distance. If p=2, it becomes Euclidean distance. It gives you the flexibility to choose the best distance type for your problem.

d) **Cosine Distance**: Instead of measuring how far apart two points are, this measures the angle between two vectors. Think of two arrows starting from the same point; if they point in the same direction, the distance is small (similarity is high), even if one arrow is much longer than the other. This is great for text analysis where the length of the document doesn't matter as much as the content.

e) **Hamming Distance**: This is used for categorical data or computer strings. It simply counts the number of positions where two strings of equal length are different. For example, the Hamming distance between "face" and "fact" is 1 because only the last letter is different. It measures the minimum number of substitutions required to change one string into the other.

f) **Chebyshev Distance**: Imagine playing chess; the King can move to any adjacent square (horizontal, vertical, or diagonal). The minimum number of moves the King needs to get from one square to another is the Chebyshev distance. Mathematically, it is simply the greatest single difference along any coordinate dimension.

#### 4. What is the role of cross validation in model performance? 

Cross-validation is a technique used to assess how well a model generalizes to unseen data. Its roles include:
- **Reducing overfitting**: By training and testing on different subsets, it detects models that memorize training data rather than learning general patterns.
- **Hyperparameter tuning**: Helps select the best value of *k* in KNN or the number of clusters in K-Means.
- **Reliable performance estimation**: Provides a more robust estimate of model accuracy than a single train-test split, since every data point is used for both training and testing across different folds.


#### 5. Explain variance and bias in terms of KNN? 

- **Bias** refers to errors due to overly simplistic assumptions in the model. In KNN, a **large value of k** (e.g., k = N) leads to **high bias** because the model averages over too many neighbors, effectively underfitting and ignoring local patterns.
- **Variance** refers to sensitivity to fluctuations in the training data. A **small value of k** (e.g., k = 1) leads to **high variance** because the prediction depends on a single neighbor and is very sensitive to noise.
