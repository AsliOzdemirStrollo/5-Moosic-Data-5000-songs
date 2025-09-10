# 🎵 Moosic Data: 5000 Songs  

## Data Science Project — WBS Coding School  
This project builds on a small 10-song experiment and scales up to a 5,000-song dataset.  
The goal is to group tracks into playlists and moods using unsupervised learning — mainly **K-Means with PCA** — and to compare results with DBSCAN and Agglomerative Clustering.  

## 📂 Repository Contents
- 📓 **Project_10_songs.ipynb** — first pass on a 10-song dataset  
- 📓 **Project_5000_songs.ipynb** — full workflow (K-Means + PCA, DBSCAN)  
- 📓 **Team_Moosic_Project_5000.ipynb** — Agglomerative Clustering + visuals  
- 📂 **2_spotify_10_songs.csv**, **spotify_5000_songs.csv** — datasets  
- 📑 [**MOOSIC project presentation (PDF)**](./MOOSIC%20project%20presentation.pdf)  

## 🎯 Objective  
Create meaningful playlists and mood groups from Spotify audio features by:  
- Reducing dimensionality with PCA  
- Clustering with K-Means (main method)  
- Comparing with DBSCAN and Agglomerative methods  
- Starting small (10 songs) → scaling to 5,000 songs  

## 🧑‍💻 Approach  

### ✅ Final Workflow Summary  
1. **Load + clean data**  
   - Deleted non-numerical & categorical columns (`id`, `artist`, `type`, etc.).  
   - Kept only numerical audio features.  
   - Set **song names as the index**.  

2. **Scale features**  
   - Tried multiple scalers: Standard, MinMax, Robust, Power, Quantile.  
   - Selected **Quantile Transformer** for handling skewed distributions.  

3. **PCA → reduce dimensions**  
   - Reduced high-dimensional data into principal components.  
   - Checked explained variance to decide components.  

4. **Cluster**  
   - **K-Means (k=20)** → tidy, balanced playlists (*Project_5000_songs.ipynb*).  
   - **UMAP + DBSCAN** → natural clusters + outliers (*Project_5000_songs.ipynb*).  
   - **Agglomerative** → hierarchical relationships (*Team_Moosic_Project_5000.ipynb*).  

5. **Visualize clusters**  
   - PCA scatterplots, t-SNE, UMAP, dendrograms.  
   - Compared results across methods.  

6. **Interpret clusters → musical meaning**  
   - Named playlists (e.g., *Chill Acoustic*, *Dance Pop*, *Fast Rap*, *Experimental Instrumental*).  
   - Printed **mood/style summaries** such as:  
     - *Happy / Danceable / Vocal-Forward / Slow / Chill*  
     - *Not Dancey / Energetic / Dark/Moody / Instrumental*  

## 🎧 Results  
- **K-Means + PCA** → 20 tidy playlists, balanced, interpretable.  
- **DBSCAN + UMAP** → mood-rich clusters with outliers.  
- **Agglomerative** → genre/subgenre hierarchy, less practical at 5,000 songs.  

💡 Key insight:  
- K-Means = tidy & structured.  
- DBSCAN = faithful & mood-based.  
- Agglomerative = shows relationships.  

## 🛠 Tools Used  
1. Python (Pandas, scikit-learn, Matplotlib, Seaborn, UMAP, t-SNE)  
2. JupyterLab  
3. Spotify datasets (10 songs, 5000 songs)  

## 📊 Presentation  
See slides here: [MOOSIC project presentation (PDF)](./MOOSIC%20project%20presentation.pdf)  

## 🎓 Key Learnings  
1. Explored several **scaling methods** and chose Quantile Transformer for this dataset.  
2. Learned the importance of proper **data preparation**.  
3. Translated technical clusters into **business insights** (playlists & moods).  
4. Practiced starting small (10 songs) before scaling up (5000 songs).  
5. Compared dimensionality reduction methods (PCA, t-SNE, UMAP) for different perspectives.  
6. Collaboration on *Team_Moosic_Project_5000.ipynb* enriched results with extra methods & visuals.  
