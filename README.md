# Song Radio Playlist Generator

**Author:** Duy Phan  
**Date:** March 20, 2025  
**Course:** Multivariate Statistics, VU Amsterdam  

## Project Summary  
This project builds an automated “song radio” playlist of 20 tracks most similar to a given reference song, based on audio features. Using a dataset of 3,090 songs with standardized values for danceability, energy, loudness, and tempo, we apply a **Gaussian Mixture Model (GMM)** to discover latent clusters and recommend songs from the same cluster as the reference.

## Problem Statement  
Music recommendation systems often rely on genre or user behavior. This project explores a **feature‑driven clustering approach** to group songs by their acoustic properties and generate a playlist that matches the style and intensity of a chosen track.

## Approach  
- **Data Standardization:** Normalize four features (danceability, energy, loudness, tempo) to zero mean and unit variance.  
- **GMM Clustering:**  
  - Fit a 5‑component Gaussian Mixture Model using the **Expectation–Maximization (EM)** algorithm.  
  - EM steps:
    - **E‑step:** Compute posterior probabilities of cluster membership.  
    - **M‑step:** Update component parameters to maximize expected log‑likelihood.  
- **Cluster Interpretation:**  
  - Analyze component means and weights to label clusters (e.g., mellow pop, energetic rock).  
  - Visualize cluster separation using energy vs. loudness scatter plot.  
- **Playlist Construction:**  
  - Use “Detonation” by Trivium as the reference song.  
  - Identify its most probable cluster (Cluster 5, posterior probability ≈ 0.604).  
  - Rank all songs in that cluster by posterior probability and select the top 20.

## Results  
- **Cluster 2 (30.9%)**: Upbeat pop songs with moderate loudness and tempo.  
- **Cluster 3 (23.1%)**: High‑energy rock/metal tracks with strong loudness and tempo.  
- **Cluster 5** (reference cluster): Loud, intense metal songs with slightly slower tempo.  
- Final playlist includes tracks like:
  - “My Life for Yours” – Killswitch Engage  
  - “Hells Bells” – AC/DC  
  - “Reclamation” – Lamb of God  
  - “This Side of Fate” – Alter Bridge  
  - “Forgotten Faces” – Avenged Sevenfold  

## Key Takeaways  
- GMM clustering provides a flexible, probabilistic way to group songs by audio features.  
- Posterior probabilities offer a natural ranking mechanism for playlist generation.  
- The resulting playlist successfully captures the **intensity and style** of the reference track, demonstrating the potential of unsupervised learning in music recommendation.
