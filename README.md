# Real-Time Music Recommendation using Pyspark and Kafka

### ✯ Introduction
* Suggesting different songs or musical artists to a user is important to many music streaming services, such as Pandora and Spotify.
* Users tend to prefer platforms with good recommendations of their taste in music.
* In this project, we have created a recommender system that will recommend new musical artists to a user based on their listening history.
* In addition, this type of recommender system could also be used as a means of suggesting TV shows or movies to a user (e.g., Netflix).

### ✯ Motivation
* In 2021, recorded streaming revenue alone exceeded $16.9 billion—with Spotify leading the way.
* Spotify paid music rights holders more money than ever in 2021: $7+ billion
* The world-class recommendations and availability of an enormous number of songs made music streaming platforms a go-to option.

### ✯ Methodology
<img width="1490" alt="Screenshot 2022-09-24 at 2 21 59 PM" src="https://user-images.githubusercontent.com/54806252/192089400-c59d3ee2-c970-4c70-b5ef-b4c44c03e0d7.png">

#### ✯ Kafka Streaming
* Kafka acts as a producer. 
* It streams a message as a batch or a single data item (we stream single data item per message).

#### ✯ PySpark with Kafka Integration
* Start the Kafka streamer (acting as producer) - pass the dataset path there.

` spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.1.0 producer.py `

* Kafka topic needs to be created before passing it to PySpark API: (using the command below)


`./bin/kafka-topics.sh localhost:2181 -topic demo -create`



### ✯ Dataset Description
<img width="335" alt="image" src="https://user-images.githubusercontent.com/54806252/192089473-0929dc0d-f66f-4e80-b578-76f8b5ce3837.png">

#### ✯ Spotify Dataset 1921 - 2020, 600+ tracks
Metadata:

Tracks covered: 1921-2020, 600k+ Tracks
Artists covered: 1M+
Source: Spotify Web API
Creator: Yamac Eren Ay
Dataset Type: CSV


Data Discription:

Total columns: 20 (example: id, name, popularity, duration_ms, artists, id_artists, energy, release_date, danceability, etc.)
Dataset Size:  508.84 MB

### ✯ Recommendation System
<img width="297" alt="image" src="https://user-images.githubusercontent.com/54806252/192209093-cec3adbc-1ea9-4aee-a0d5-3d0d88153b04.png">

* In this project we have used ALS Implicit Collaborative Filtering for recommendations.
* Alternating Least Squares(ALS) is an iterative optimization process where for every iteration we try to arrive closer and closer to a factorized representation of our original data.
* We used the best Model with the highest score for making recommendations.


 ### ✯ Novel Contributions
* Created Real-world streaming simulation using Kafka.
* Used state-of-the-art Collaborative Filtering approach for Recommendations.
* Integrated model with Spotify for a personalized recommendation.
* Deployed the model to a web app for better user experience.

### ✯ Results Demonstration
<img width="777" alt="image" src="https://user-images.githubusercontent.com/54806252/192090086-972c2f34-7e91-43cd-93eb-eb9c369eb70b.png">
<img width="863" alt="image" src="https://user-images.githubusercontent.com/54806252/192090095-23d3942e-f6e4-4880-bb4d-9edee1e6c8cd.png">
<img width="805" alt="image" src="https://user-images.githubusercontent.com/54806252/192090103-0dae8a66-ddb4-433c-81d1-09327a085343.png">

### ✯ References

1. PySpark: https://spark.apache.org/docs/latest/api/python/ 

2. Kaggle Dataset: https://www.kaggle.com/datasets/yamaerenay/spotify-dataset-19212020-600k-tracks 

3. Kafka Streaming: https://docs.confluent.io/platform/current/streams/index.html#:~:text=Kafka%20Streams%20is%20a%20client,Kafka's%20server%2Dside%20cluster%20technology. 

4. Streamlit: https://streamlit.io/ 

5. Spotipy API: https://github.com/plamere/spotipy 

6. KMeans Classification for Recommendation: https://www.sciencedirect.com/science/article/pii/S1875389212006220 





