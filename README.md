# fMRI Brain Connectivity Clustering

This project focuses on clustering fMRI data based on brain connectivity patterns across two brain atlases with 200 and 246 components. The goal is to group brain scans into meaningful clusters that identify unique brain functional characteristics using spectral clustering and advanced feature extraction techniques.

## Project Overview

Functional Magnetic Resonance Imaging (fMRI) measures brain activity by detecting changes in blood flow. This project processes resting-state fMRI data, applying machine learning to cluster connectivity matrices between brain regions. The method extracts statistical patterns from time series data, balances the samples, and creates 20 clusters, each containing 16 samples.

### Key Features:
- **Two Brain Atlases**: Data processed using brain atlases with 200 and 246 components.
- **Feature Extraction**: Standard deviations and differences between time windows capture meaningful brain activity.
- **Spectral Clustering**: Algorithm groups brain scans into balanced clusters, ensuring each cluster contains 16 samples.
- **KNN Imputation**: Used to handle missing values in the dataset.
- **Dimensionality Reduction**: Truncated SVD is applied to reduce the feature space before clustering.

## How It Works

1. **Data Preprocessing**: 
   - The fMRI data is initially cleaned using KNN imputation to handle any missing values in the brain atlas components.
   - Data from two atlases (with 200 and 246 components) is separated based on the presence of NaNs in the dataset. 
   
2. **Feature Extraction**: 
   - For each sample, we calculate the standard deviation across brain regions and the difference between the first 10 and the last 10 time points.
   - These features are combined to form feature vectors, which represent brain connectivity patterns over time.
   
3. **Dimensionality Reduction**: 
   - Truncated SVD (Singular Value Decomposition) is applied to reduce the dimensionality of the feature space while retaining the most important components for clustering.
   
4. **Spectral Clustering**: 
   - Spectral clustering is used to group the fMRI samples into 20 clusters, ensuring that each cluster has exactly 16 samples.
   - Clustering is performed on the reduced feature vectors, using the radial basis function (RBF) kernel to measure similarities.
   
5. **Balanced Clustering**: 
   - After clustering, pairs of samples are merged and sorted into two arrays corresponding to the two brain atlases, maintaining cluster balance.

## Results

- The project successfully clusters the fMRI brain connectivity data into 20 distinct groups, each containing 16 samples.
- Spectral clustering reveals clear groupings based on brain connectivity patterns, identifying unique features of individual brain profiles.
- The approach ensures that data from both brain atlases are treated equitably and that each cluster maintains a balanced representation.

## Contributing

Contributions are welcome! If you encounter any issues or have ideas for improvement, please feel free to:

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Submit a pull request for review.

Any feedback, suggestions, or improvements are greatly appreciated!

