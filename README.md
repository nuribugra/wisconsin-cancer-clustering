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

Results:
The analysis to determine the optimal number of clusters using both the Elbow Method and Silhouette Score strongly indicated that K=2 is the most appropriate choice for this dataset. The models were then implemented and evaluated based on this finding.

K-Means Performance: The K-Means algorithm performed exceptionally well. When its predicted clusters were compared against the true diagnostic labels, it achieved an accuracy of 91.21%. The PCA visualization confirmed this success, showing two well-separated clusters that visually corresponded almost perfectly to the actual malignant and benign groups.

DBSCAN Performance: The DBSCAN algorithm, after parameter tuning, was found to be ineffective for this particular problem. The optimal eps value was determined to be approximately 4.5. However, the model identified only one major cluster, failing to distinguish between the two classes. This was confirmed by very low evaluation scores, including an Adjusted Rand Score of 0.0260 and a Homogeneity Score of 0.0091 (where 1.0 is a perfect match and 0 is random). The PCA plot for DBSCAN showed a single large group with several noise points, unlike the clear separation achieved by K-Means.

Conclusion:
This project demonstrates that the success of a clustering algorithm is highly dependent on the structure of the data.

K-Means, a centroid-based algorithm, was successful because the two clusters (malignant and benign) are globular and have distinct centers. DBSCAN, a density-based algorithm, failed because these two clusters are located close to each other without a significant low-density area separating them, causing the algorithm to perceive them as a single, large dense region.

Ultimately, this analysis shows that unsupervised learning can be a powerful tool for discovering inherent patterns in medical datasets. However, it also highlights the critical importance of selecting an appropriate algorithm that matches the data's underlying distribution to achieve meaningful results.

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