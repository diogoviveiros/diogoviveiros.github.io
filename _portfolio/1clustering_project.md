---
title: "Topic Similarity Clustering"
excerpt: "Python app with Flask Web UI for clustering topics from CSV files using a transformer word vectorisation combined with hierarchichal clustering methods. (2025)"
collection: portfolio
---

[View Project on Github](https://github.com/diogoviveiros/Topic-Similarity-Clustering)

This project is a Flask-based web app that performs topic clustering through uploading a CSV file — ideal for grouping together projects, themes, or other elements from comma separated files.

It implements a transformer architecture-based word embedder to transform each row of text-based data into a vector located in a pre-trained dataset that has learned contextual queues. We can then compare the cosine similarity between all the vectors in relation to each other in order to get the relevant distance between embeddings, telling us how contextually similar these texts are. Cosine similarity is calculated by taking the dot product of two vectors and divide them by the product of their magnitudes, allowing us to know where a vector is in relation to another. Once the similarities are calculated, we get scores between 0 and 1, where the higher score notes a closer match. We can then take an agglomerative clustering algorithm to group these scores either based on number of clusters or by setting a specific threshold of *1 - cosine_similarity*, and then have the algorithm figure out how many clusters should exist. For example, if we want clusters where the cosine similarity between all rows is 0.65 or higher, we would input a threshold of 0.35. The algorithm then performs the clustering and outputs a CSV file to be downloaded.    

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
