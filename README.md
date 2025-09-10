<h1>🎵 Moosic Data: 5000 Songs</h1>

<h2>Data Science Project — WBS Coding School</h2>
<p>
  This project builds on a small 10-song experiment and scales up to a 5,000-song dataset.
  The goal is to group tracks into playlists and moods using unsupervised learning—
  mainly <strong>K-Means with PCA</strong>—and to compare results with other clustering approaches.
</p>

<h3>Repository Contents</h3>
<ul>
  <li>📓 <strong>Project_10_songs.ipynb</strong> — first pass on a 10-song dataset</li>
  <li>📓 <strong>Project_5000_songs.ipynb</strong> — full workflow (K-Means + PCA, DBSCAN)</li>
  <li>📓 <strong>Team_Moosic_Project_5000.ipynb</strong> — Agglomerative Clustering + visuals</li>
  <li>📂 <strong>2_spotify_10_songs.csv</strong>, <strong>spotify_5000_songs.csv</strong> — datasets</li>
  <li>📑 <strong><a href="./MOOSIC%20project%20presentation.pdf">MOOSIC project presentation (PDF)</a></strong></li>
</ul>

<hr/>

<h2>🎯 Objective</h2>
<p>
  Create meaningful playlists and mood groups from Spotify audio features by:
  reducing dimensionality with PCA, clustering with K-Means, and comparing with DBSCAN and Agglomerative methods.
  Start small (10 songs) → scale to real-world size (5,000 songs).
</p>

<h2>🎼 Dataset Features</h2>
<p>Each track includes: acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, loudness, mode, speechiness, tempo, time_signature, valence.</p>

<h2>🛠 Tools Used</h2>
<ul>
  <li>Python (Pandas, scikit-learn, Matplotlib, Seaborn, UMAP, t-SNE)</li>
  <li>JupyterLab</li>
  <li>Spotify audio-feature datasets (10 &amp; 5,000 songs)</li>
</ul>

<hr/>

<h2>🧑‍💻 Approach</h2>

<h3>✅ Final Workflow Summary</h3>
<ol>
  <li><strong>Load + clean data</strong>
    <ul>
      <li>Deleted non-numerical &amp; categorical columns (e.g., <code>id</code>, <code>artist</code>, <code>type</code>).</li>
      <li>Kept only numerical audio features for clustering.</li>
      <li>Set <strong>song names as the index</strong> for readability.</li>
    </ul>
  </li>
  <li><strong>Scale features</strong>
    <ul>
      <li>Tried multiple scalers: <em>Standard</em>, <em>MinMax</em>, <em>Robust</em>, <em>Power</em>, <em>Quantile</em>.</li>
      <li>Chose <strong>Quantile Transformer</strong> to handle skewed distributions fairly.</li>
    </ul>
  </li>
  <li><strong>PCA → reduce dimensions</strong>
    <ul>
      <li>Compressed features to principal components and reviewed explained variance.</li>
    </ul>
  </li>
  <li><strong>Cluster</strong>
    <ul>
      <li><strong>K-Means (k=20)</strong>: main method; evaluated with silhouette scores. <em>(Project_5000_songs.ipynb)</em></li>
      <li><strong>UMAP + DBSCAN</strong>: natural clusters + outliers. <em>(Project_5000_songs.ipynb)</em></li>
      <li><strong>Agglomerative Clustering</strong>: hierarchical view. <em>(Team_Moosic_Project_5000.ipynb)</em></li>
    </ul>
  </li>
  <li><strong>Visualize clusters</strong>
    <ul>
      <li>PCA scatterplots (presentation-friendly), t-SNE, UMAP; dendrograms for hierarchical results.</li>
      <li>Compared groupings across methods.</li>
    </ul>
  </li>
  <li><strong>Interpret clusters → musical meaning</strong>
    <ul>
      <li>Named playlists (e.g., <em>Chill Acoustic</em>, <em>Dance Pop</em>, <em>Fast Rap</em>, <em>Experimental Instrumental</em>).</li>
      <li>Printed mood/style summaries like <em>Happy / Danceable / Vocal-Forward / Slow / Chill</em> and
          <em>Not Dancey / Energetic / Dark/Moody / Instrumental</em>.</li>
    </ul>
  </li>
</ol>

<hr/>

<h2>🎧 Results (Summary)</h2>
<ul>
  <li><strong>K-Means + PCA</strong>: 20 tidy, balanced playlists; easy to interpret.</li>
  <li><strong>DBSCAN + UMAP</strong>: natural, mood-rich clusters; includes outliers.</li>
  <li><strong>Agglomerative</strong>: reveals genre/subgenre relationships; less practical at 5,000+ songs.</li>
</ul>
<p><em>See the slides for visuals:</em> <a href="./MOOSIC%20project%20presentation.pdf">MOOSIC project presentation (PDF)</a></p>

<hr/>

<h2>🎓 Key Learnings</h2>
<ul>
  <li>Explored several <strong>data scaling methods</strong> and selected the most suitable one for this data.</li>
  <li>Good <strong>data preparation</strong> is essential before applying machine learning.</li>
  <li>Translated technical clusters into <strong>business-relevant insights</strong> (playlists &amp; moods).</li>
  <li>Starting with a 10-song set helped test ideas before scaling to 5,000 songs.</li>
  <li>Different dimensionality-reduction &amp; visualization methods (PCA, t-SNE, UMAP) offer complementary views.</li>
  <li>Team collaboration (<em>Team_Moosic_Project_5000.ipynb</em>) strengthened methods &amp; visuals.</li>
</ul>
