# Unsupervised Machine Learning & Deep Learning Pipeline

<p align="center">
  <a href="https://sohail.devsil.com"><strong>Portfolio</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh/unsupervised-deep-learning-pipeline"><strong>Source Repository</strong></a>
</p>

---

## Executive Summary & Problem Statement

Over 80% of enterprise data is unlabelled, unstructured, and high-dimensional. Supervised learning techniques fail in scenarios where ground truth annotations are prohibitively expensive, scarce, or unknown. Organizations require rigorous unsupervised learning architectures capable of uncovering latent patterns, clustering natural cohorts, and isolating anomalous events.

This repository implements an end-to-end **Unsupervised Machine Learning and Deep Learning Pipeline**. It bridges classical statistical dimensionality reduction (**PCA**, **t-SNE**, **K-Means**, **GMM**) with modern neural architectures (**Deep Autoencoders**) for latent feature discovery and anomaly isolation.

<div align="center">
  <img src="https://raw.githubusercontent.com/sohailahmed-bsrh/myportfolio/main/assets/images/thumbnail/unsupervised-ml-deep-learning.jpeg" width="650" alt="Unsupervised Machine Learning & Deep Learning"/>
  <p><em>Latent space representation, manifold learning, and deep autoencoder anomaly detection.</em></p>
</div>

---

## Real-World Industry Applications

- **Customer Behavioral Segmentation**: Identifies organic buyer personas from unlabelled transactional history to optimize marketing spend.
- **Financial Fraud & Anomaly Detection**: Employs deep autoencoder reconstruction error thresholds to flag fraudulent transactions without historical fraud labels.
- **Genomic & High-Dimensional Data Compression**: Compresses multi-thousand gene expression profiles into orthogonal components via PCA and t-SNE.
- **Network Intrusion Detection**: Flags zero-day cyber threats deviating significantly from normal latent network traffic distributions.

---

## Technical Architecture & Engineering Walkthrough

```
                      [High-Dimensional Unlabelled Dataset]
                                        │
                                        ▼
             [Feature Standardization & Rigorous Outlier Scaling]
                                        │
         ┌──────────────────────────────┼──────────────────────────────┐
         ▼                              ▼                              ▼
[Dimensionality Reduction]      [Cohort Clustering]          [Deep Autoencoder]
   (PCA & t-SNE Manifold)      (K-Means & GMM Latents)       (Bottleneck Compression)
         │                              │                              │
         ▼                              ▼                              ▼
[Orthogonal Variance Vectors]    [Optimal K Validation]       [Reconstruction Loss]
(Elbow Variance Plots)           (Silhouette & Davies-Bouldin) (Anomaly Thresholding)
```

### Step 1: Preprocessing & Scaling
High-dimensional distance metrics are distorted by variable feature magnitudes. Features are scaled using `StandardScaler` and `RigorousScaler` to ensure zero-mean and unit variance.

### Step 2: Dimensionality Reduction via PCA & t-SNE
Performs Principal Component Analysis (PCA) to calculate eigenvalues and eigenvectors of the covariance matrix. Generates scree plots demonstrating cumulative explained variance ratios. Employs t-Distributed Stochastic Neighbor Embedding (t-SNE) for non-linear manifold visualization.

### Step 3: Optimal Cluster Validation
Executes K-Means and Gaussian Mixture Models (GMM) clustering. Determines the optimal cluster count $(k)$ through mathematical consensus: Elbow Method (Inertia), Silhouette Coefficients, and Davies-Bouldin Index.

### Step 4: Deep Autoencoder Construction
Constructs a symmetrical neural autoencoder:
- **Encoder**: Progressively compresses feature dimensions into a compact bottleneck latent space.
- **Decoder**: Symmetrically reconstructs original feature vectors from the compressed latent representation.

### Step 5: Reconstruction Error Anomaly Detection
Calculates Mean Squared Reconstruction Error (MSE) between original and reconstructed vectors. Data points with reconstruction loss exceeding statistical percentiles (95th / 99th percentile) are flagged as anomalous outliers.

---

## Technology Stack & Implementation Specifications

| Component | Technology | Version | Architectural Function |
| :--- | :--- | :--- | :--- |
| **Deep Learning** | TensorFlow / Keras | 2.15+ | Bottleneck autoencoder construction and training |
| **Unsupervised ML** | Scikit-Learn | 1.3+ | PCA, t-SNE, K-Means, GMM, Silhouette evaluation |
| **Matrix Computation** | NumPy / SciPy | Latest | Covariance computation and distance matrix generation |
| **Data Ingestion** | Pandas | 2.x | Tabular parsing, missing value imputation |
| **Visualization** | Seaborn / Matplotlib | 3.8+ | 2D/3D cluster projections and reconstruction error distributions |

---

## Installation & Execution Guide

```bash
git clone https://github.com/sohailahmed-bsrh/unsupervised-deep-learning-pipeline.git
cd unsupervised-deep-learning-pipeline
python -m venv venv
# Windows: venv\Scriptsctivate | Unix: source venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/
```

---

## Author & Contact Information

<table width="100%">
  <tr>
    <td width="150" align="center" valign="middle">
      <img src="https://avatars.githubusercontent.com/u/231165170?v=4" width="120" style="border-radius: 50%;" alt="Sohail Ahmed"/>
    </td>
    <td>
      <h3>Sohail Ahmed</h3>
      <p><strong>Senior Software Engineer & AI Systems Architect</strong></p>
      <p>Specializing in Full-Stack AI Application Development, Computer Vision, Deep Learning Pipelines, and Scalable Automation Architectures.</p>
      <p>
        <a href="https://sohail.devsil.com"><strong>Portfolio Website</strong></a> | 
        <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
        <a href="https://www.linkedin.com/in/sohail-ahmed-devsil/"><strong>LinkedIn</strong></a> | 
        <a href="https://www.kaggle.com/sohail2411126"><strong>Kaggle</strong></a> | 
        <a href="https://x.com/ahmed241126"><strong>Twitter/X</strong></a> | 
        <a href="mailto:se906403@gmail.com"><strong>Email Contact</strong></a>
      </p>
    </td>
  </tr>
</table>
