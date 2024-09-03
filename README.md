# Song Recommendation System Using Spotipy and KMeans Clustering

## Overview

This project demonstrates a simple song recommendation system using Spotify's Web API, the `Spotipy` library, and `KMeans` clustering from `scikit-learn`. The script retrieves audio features for a selection of tracks from Spotify, applies clustering to group similar tracks, and provides song recommendations based on the input track.

## Features

- **Spotify API Integration**: Fetches song metadata and audio features using Spotipy.
- **Data Preprocessing**: Normalizes the song features using `StandardScaler`.
- **Clustering**: Uses `KMeans` clustering to group similar songs based on their audio features.
- **Song Recommendation**: Recommends songs from the same cluster as the input song.

## Setup

### Prerequisites

- Python 3.x
- Spotipy
- Pandas
- Scikit-learn

### Installation

Install the required Python packages using pip:

```bash
pip install spotipy pandas scikit-learn
```

### Spotify API Credentials

You need to obtain `client_id` and `client_secret` from the Spotify Developer Dashboard and replace them in the script.

```python
client_id = 'your_client_id'
client_secret = 'your_client_secret'
```

## Usage

1. **Retrieve Song Features**: The `get_song_features` function fetches metadata and audio features for a given track ID from Spotify.

2. **Data Preprocessing**: The selected song features are scaled using `StandardScaler` for clustering.

3. **KMeans Clustering**: The `KMeans` algorithm groups songs into clusters based on their audio features.

4. **Song Recommendation**: The `recommend_songs` function suggests songs from the same cluster as the input song.

### Example

Replace `track_ids` with your own list of Spotify track IDs or use the provided sample IDs. You can change the song name in the `recommend_songs` function to get recommendations for different tracks.

```python
song_name = 'Believer'
recommendations = recommend_songs(song_name, df)
print(recommendations)
```

## Limitations

- The number of clusters (`num_clusters`) is set to a minimum of 3 to prevent too few or too many clusters, but this can be adjusted based on the dataset.
- The script currently supports only a limited number of tracks. Expanding the dataset and tuning the clustering parameters can improve recommendations.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Spotipy](https://spotipy.readthedocs.io/) for providing a simple Python interface for Spotify's Web API.
- [Scikit-learn](https://scikit-learn.org/stable/) for the machine learning tools used in this project.
