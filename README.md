# Clustering Analysis of the Wisconsin Breast Cancer Dataset

![Breast Cancer](httpsosis_icon.png) ## Project Goal

This project applies unsupervised machine learning techniques, specifically clustering algorithms, to the Wisconsin Breast Cancer (Diagnostic) dataset. The primary goal is to identify natural groupings within the data and see if these clusters correspond to the actual diagnosis of malignant or benign tumors, without using the diagnosis labels during the training process.

---

## Dataset

The dataset used is the **Wisconsin Breast Cancer (Diagnostic) Dataset** from the UCI Machine Learning Repository.

- **Number of Instances:** 569
- **Number of Attributes:** 30 numeric, predictive attributes and the class.
- **Classes:** Malignant (kötü huylu) and Benign (iyi huylu).
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

---

## Methodology

The project follows these key steps:

1.  **Data Preparation:** Loading the dataset, separating features from labels, and scaling the data using `StandardScaler`.
2.  **Finding Optimal Cluster Count (K):**
    -   **Elbow Method:** Performed to find the point of diminishing returns for the number of clusters.
    -   **Silhouette Score:** Calculated to measure how well-separated the clusters are for different values of K.
    -   Both methods suggested that **K=2** is the optimal number of clusters.
3.  **Clustering Algorithms:**
    -   **K-Means:** Implemented with the optimal K=2.
    -   **DBSCAN:** Implemented to provide a density-based clustering perspective.
4.  **Evaluation:** Comparing the clusters found by the algorithms against the true labels (Malignant/Benign) to measure performance.
5.  **Visualization:** Plotting the resulting clusters in 2D space using Principal Component Analysis (PCA) for dimensionality reduction.

---

## Technologies & Libraries Used

- Python 3.x
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Results & Conclusion
<!--
Example:
The K-Means model with K=2 successfully identified two distinct clusters that showed a high correlation with the actual malignant and benign diagnoses. The DBSCAN algorithm also found similar groupings, confirming the inherent structure in the data. This demonstrates the potential of unsupervised learning in identifying meaningful patterns in medical datasets.
-->

---

## How to Run

1.  Clone the repository:
    ```bash
    git clone [https://github.com/YOUR_USERNAME/wisconsin-cancer-clustering.git](https://github.com/YOUR_USERNAME/wisconsin-cancer-clustering.git)
    ```
2.  Navigate to the project directory:
    ```bash
    cd wisconsin-cancer-clustering
    ```
3.  (Optional but recommended) Create a virtual environment.
4.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
5.  Open the Jupyter Notebook in the `notebooks/` directory and run the cells.
    ```bash
    jupyter notebook notebooks/main.ipynb
    ```