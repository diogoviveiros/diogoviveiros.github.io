---
title: "Topic Similarity Clustering"
excerpt: "Flask app for clustering topics from CSV files using a transformer word vectorisation combined with hierarchichal clustering methods."
collection: portfolio
---

[View Project on Github](https://github.com/diogoviveiros/Topic-Similarity-Clustering)

This project is a Flask-based web app that performs topic clustering through uploading a CSV file — ideal for grouping together projects, themes, or other elements from comma separated files. 

# How It Works
- Upload a `.csv` file. Make sure that there are two columns called `Title` and `Description`. These two columns will be merged into one group of sentences.
- We clean the `Title` and `Description` columns using REGEX and Pandas to remove any potential formatting issues.
- We then remove stop-words (common words like "and", "it", "but", etc) to keep the topic's context while also creating higher differences for our model to distinguish from.
- Once cleaning is done, we run a transformer model to tokenize the text and create a vector embedding for each topic.
- Once the text is tokenized, we can now calculate the cosine distance between the embeddings to get a similarity score. 
- We can now run hierarchichal agglomerative clustering on the similarity scores to create our clusters. Through Flask, the user can choose whether they want the clustering algorithm to find them an appropriate number of clusters based on a specific sensitivity threshold or if they just want a fixed number of clusters.

# Outcomes
- **Speed:** The transformer model is fairly robust while also being performant. 350 different rows of data can be vectorized in approximately one minute.  
- **Flexibility:** Clustering choices allow for user to customize their thresholds and number of clusters to get an output that's best for their needs.
- **Practicality:** Useful for clustering topics such as articles, internal projects, grouping feedback, and more.

# Demo Video

<video width="100%" controls>
  <source src="/images/TopicClusteringDemo480.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
