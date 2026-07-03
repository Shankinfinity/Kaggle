Exploring Hidden Structures in CERN Collision Data (PCA + K-Means)

This project analyzes 100,000 real electron-positron collision events recorded at CERN, using Principal Component Analysis (PCA) and K-Means clustering to uncover hidden structure in the data — without relying on labeled categories. The dataset includes each electron's energy, momentum components, transverse momentum, pseudorapidity, azimuthal angle, and charge, along with the invariant mass of the electron pair.

Data


Source: CERN Electron Collision Data (Kaggle)
100,000 dielectron collision events, 19 variables per event
Key features: E1/E2 (energy), px/py/pz (momentum), pt1/pt2 (transverse momentum), eta1/eta2 (pseudorapidity), phi1/phi2 (angle), Q1/Q2 (charge), M (invariant mass)


Workflow


EDA – examined the invariant mass distribution, energy and transverse momentum distributions, and feature correlations.
Preprocessing – standardized all kinematic variables; excluded invariant mass (M) from PCA since it's derived from the other features.
PCA – reduced the 16 kinematic variables to their principal components, examined explained variance, and interpreted feature loadings for the top components.
Clustering – applied K-Means (using the Elbow Method to select k) on the PCA-reduced feature space to group collision events by kinematic similarity.
Interpretation – examined invariant mass and energy distributions across the resulting clusters.


Key Findings


The invariant mass distribution shows a clear peak near 90 GeV, consistent with the Z boson resonance — confirming the data reflects real physical collision events.
The first 2 principal components explain only ~27% of total variance; ~10 components are needed to retain ~89%, showing the data has a fairly complex, high-dimensional structure.
The top principal components are driven mainly by pseudorapidity (η) and longitudinal momentum (pz), followed by transverse momentum components (py, phi).
The Elbow Method suggested k = 6 clusters. K-Means grouped events primarily by kinematic similarity (energy, momentum, angle) rather than by invariant mass — expected, since mass was excluded from the clustering features.


Skills Demonstrated


Exploratory data analysis on real particle physics data
Dimensionality reduction with PCA (explained variance, loadings interpretation)
Unsupervised clustering with K-Means and the Elbow Method
Data visualization (histograms, correlation heatmaps, scatter plots, boxplots)
Physical interpretation of statistical/ML results in a scientific context
