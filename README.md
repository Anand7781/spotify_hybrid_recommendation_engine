# Spotify Hybrid Recommendation Engine

## Project Overview

This project is an **end-to-end Spotify-style music recommendation engine** for real-time and effective content delivery.

It uses a **hybrid approach** by combining:

- Content-Based Recommendation Engine  
- Collaborative Filtering Recommendation Engine  

The system delivers **personalized, accurate, and diverse music recommendations** by analyzing both music attributes and user behavior.

---

## Objectives

- Build a hybrid recommender system using content and collaborative signals.
- Use audio features, tags, genres, and user behavior for improved predictions.
- Handle cold-start problems for new users and new songs.
- Design a real-time deployable architecture.
- Provide API-based access for external applications.

---

## System Architecture

1. Data Layer  
   - Track metadata  
   - User listening history  
   - Spotify audio features  
   - Genre and tag annotations  

2. Processing Layer  
   - Data cleaning and preprocessing  
   - Feature normalization  
   - Categorical encoding  
   - User–item interaction matrix creation  

3. Model Layer  
   - Content-based recommender  
   - Collaborative filtering model  
   - Hybrid fusion model  

4. Serving Layer  
   - REST API backend  
   - Frontend interface  
   - Model inference  

---

## Dataset Description

The dataset used in this project is a rebuilt subset of the **Million Song Dataset**, combined with multiple external sources.

### Data Sources

- Million Song Dataset  
- Echo Nest Taste Profile Subset  
- Last.fm Dataset (2020)  
- Lastfm-Spotify-Tags-Sim-Userdata  
- Tagtraum genre annotations  
- Spotify Web API  

### Dataset Statistics

- Total Songs: 50,683  
- User Interactions: 9,711,301  
- Audio Samples: 1,500 tracks  
- Genres: 15  
- Songs per Genre: 100  

### Typical Columns

- track_id  
- name  
- artist  
- spotify_id  
- genre  
- tags  
- duration_ms  
- danceability  
- energy  
- tempo  
- loudness  
- valence  
- acousticness  
- instrumentalness  
- liveness  
- speechiness  
- user_id  
- listen_count  

---

## Recommendation Techniques

### Content-Based Filtering

Recommends songs based on similarity between tracks.

Features used:

- Audio features from Spotify  
- Genre labels  
- Tags from Last.fm  
- Artist metadata  

Methods applied:

- Feature vector construction  
- Normalization and scaling  
- Cosine similarity for similarity measurement  

Advantages:

- Works without user history  
- Provides song-level similarity  

Limitations:

- Limited diversity  
- Cannot discover unseen user preferences  

---

### Collaborative Filtering

Recommends songs based on user interaction patterns.

Data used:

- User-song interaction history  
- Implicit feedback signals  

Models used:

- SVD (Singular Value Decomposition)  
- ALS (Alternating Least Squares)  
- KNN-based similarity models  

Advantages:

- Discovers hidden user patterns  
- Offers diverse recommendations  

Limitations:

- Cold-start problem  
- Requires large interaction data  

---

### Hybrid Recommendation Engine

The system combines both approaches using weighted fusion.

