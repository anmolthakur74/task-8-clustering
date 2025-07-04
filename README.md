# Task 8: K-Means Clustering

This repository contains my solution for **Task 8** of the AI & ML Internship. The task focuses on implementing the **K-Means clustering algorithm** using the **Mall_Customers.csv** dataset to group customers into distinct segments based on their behavior.

---

## Objective

Perform unsupervised learning with K-Means clustering.

---

## Files Included

| File Name             | Description                                                           |
|----------------------|-----------------------------------------------------------------------|
| `Mall_Customers.csv` | Dataset used for clustering                                           |
| `clustering.ipynb`   | Jupyter Notebook with implementation, Elbow method, and visualization |
| `screenshots/`       | Folder containing plots and cluster visualizations                    |
| `README.md`          | Project documentation                                                 |

---

## What I Did

### 1. Dataset Loading and Exploration

I started by loading the `Mall_Customers.csv` dataset using pandas. The dataset contains customer-related information such as `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, and `Spending Score (1-100)`. I focused on `Annual Income` and `Spending Score` as the key features for clustering since these provide useful insight for business segmentation.

I also performed a quick exploration using `.head()`, `.info()`, and `.describe()` to ensure the data was clean and didn’t contain missing values. These checks confirmed the dataset was well-structured and ready for clustering.

### 2. Feature Selection and Scaling

Since K-Means uses distance-based calculations, I standardized the selected features (`Annual Income` and `Spending Score`) using `StandardScaler`. This ensures that one feature doesn't dominate due to scale differences.

### 3. Model Training with K-Means

I applied the KMeans algorithm from `sklearn.cluster`, starting with an arbitrary choice of K = 5. After fitting the model, I assigned each data point to one of the 5 clusters and added this cluster information back into the dataset. This gave a first glimpse into how the data points were grouped.

### 4. Optimal K using Elbow Method

To determine the best number of clusters, I implemented the **Elbow Method** by plotting the Within-Cluster Sum of Squares (WCSS) for different values of K (from 1 to 10). The "elbow point" where the WCSS starts to decrease slowly indicated the optimal value for K, which in my case was 5.

### 5. Cluster Visualization

Using matplotlib and seaborn, I plotted the data points with color-coded cluster labels to visualize how the customers were grouped. This helped me observe distinct segments—like high spenders with low income, or low spenders with high income—enabling better marketing insights.

### 6. Evaluation with Silhouette Score

Finally, I evaluated the quality of the clustering using the Silhouette Score, which measures how well-separated the clusters are. A score close to 1 indicates clearly defined clusters, while a score closer to 0 suggests overlapping clusters.

For K = 5, the Silhouette Score was: 0.5547
This indicates a moderate level of cluster separation, meaning that the clusters are fairly well-formed, but there's still some overlap—especially between groups with similar spending behavior or income levels.

---

## What I Learned

This task helped me:

- Understand how **K-Means** clustering groups similar data points without using labels.
- Apply **feature scaling** to improve clustering performance.
- Use the **Elbow Method** to find an optimal number of clusters.
- Visualize clusters meaningfully to gain business insights.
- Evaluate cluster quality using **Silhouette Score**.
- Realize the practical applications of unsupervised learning in customer segmentation and business strategy.

---

## Libraries Used

- Python 3.12  
- `pandas`, `numpy` — for data loading and processing  
- `matplotlib`, `seaborn` — for visualizations  
- `scikit-learn` — for clustering

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/task-8-kmeans-clustering.git
   cd task-8-kmeans-clustering

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn

4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook clustering.ipynb

## Author

**Anmol Thakur**

GitHub: [anmolthakur74](https://github.com/anmolthakur74/)
