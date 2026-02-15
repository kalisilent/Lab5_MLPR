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

## Visualizations
*(Please refer to the notebook output cells for the actual generated plots)*
- **Detected Faces**: Faces in the original image are marked with rectangles.
- **Feature Scatter Plot**: A plot showing Hue vs. Saturation for all faces.
- **Clustering Result**: Points colored by cluster label (Green vs. Blue) with distinct centroids.
- **Template Classification**: The template image is plotted as a distinct point (Violet) to show its relationship to the learned clusters.

## Code Structure
- `Lab 5-Spring 2026.ipynb`: The main Jupyter Notebook containing all python code, output visualizations, and answers to the report questions.
- `plaksha_Faculty.jpg`: Input image for group face detection.
- `Dr_Shashi_Tharoor.jpg`: Template image for classification.

## Report Report Questions
The notebook includes detailed answers to the 5 report questions regarding distance metrics, real-world applications of distance-based algorithms, and the bias-variance tradeoff in KNN.
