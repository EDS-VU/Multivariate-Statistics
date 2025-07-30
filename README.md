# Song Radio Playlist Generator

**Author:** Duy Phan  
**Date:** March 20, 2025  
**Course:** Multivariate Statistics, VU Amsterdam  

## Overview  
This project builds an automated “song radio” playlist of 20 tracks that are most similar—by audio features—to a given reference song. Using a dataset of 3,090 songs (with standardized measures of danceability, energy, loudness, and tempo), we apply a Gaussian Mixture Model (GMM) to discover clusters of similar tracks and then recommend the top 20 from the same cluster as the reference.

## Methodology  
1. **Data Preparation**  
   - Standardize four numeric features: danceability, energy, loudness, and tempo.  
2. **Clustering with GMM**  
   - Fit a 5‑component Gaussian mixture model via the Expectation–Maximization (EM) algorithm.  
   - In each EM iteration:
     - **E‑step:** Compute posterior probabilities of cluster membership for each song.  
     - **M‑step:** Update component means, covariances, and weights to maximize expected log‑likelihood. 
3. **Cluster Interpretation**  
   - Examine component means and weights to label clusters (e.g., “energetic rock,” “mellow pop”).  
   - Visualize overlap and separation along energy vs. loudness.  
4. **Playlist Construction**  
   - Select a reference song (“Detonation” by Trivium), identify its most probable cluster, then rank all songs in that cluster by their posterior probabilities.  
   - Output the top 20 as the recommended radio playlist.

## Key Findings  
- **Dominant Cluster (30.9%)** corresponds to upbeat pop with moderate loudness and tempo.  
- **High‑energy cluster (23.1%)** captures rock/metal tracks with strong loudness and tempo.  
- The playlist of 20 songs (e.g., “My Life for Yours,” “Hells Bells,” “Reclamation”) reliably matches the intense, metal style of the reference. 


