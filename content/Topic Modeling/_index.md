---
title: "Topic Modeling"
description: "Modeling Science Fiction with Gensim LDA and BERTopic"
cascade:
  featured_image: '/images/lda_1.png'
menu:
  main:
    weight: 1
---
**LDA (Gensim) Topic Modeling** is based on the assumption that documents are a mixture of topics (# topics is set by the researcher) and that topics are a mixture of words. To determine which words belong to each topic, the LDA model randomly assigns each word in a set of documents to a topic, then iterates through the assignments and makes adjustments until all words are assigned to the topics where they have the highest probability of belonging. LDA topic modeling works well on disaggregated texts (like the dataset generated above). 

Using C_V and U_Mass Coherence calculations, we determined that optimal number of topics for the sci-fi collection was 178. In other words, a model with 178 topics provides the most coherent co-occurences of words and documents in each topic. Prior to this analysis, all stopwords and non-English words were removed. Here are the most frequent words present in the top topics in the model (access full dataframe [here](https://github.com/SF-Nexus/extracted-features/blob/main/data/LDA_output/LDA_topics_keywords_df.csv)).

![image](/src/code/lda_topic_keywords.png "lda_topic_keywords")

**BERTopic Topic Modeling** is a topic modeling tool which creates topic clusters based on word embeddings and a class-based TF-IDF. It generates a set of topics, the top words in each topic, and the likelihood of each text in a corpus belonging to each topic. Because it makes use of word embeddings, it does not work well with disaggregated texts. 

Unlike LDA, BERTopic automatically chooses the number of topics to generate within the model, though parameters can be set to collapse extremely similar topics. Performing BERTopic modeling on the sci-fi corpus yielded 68 topics, excluding Outliers (access full dataframe [here]

![image](/src/code/lda_topic_keywords.png "lda_topic_keywords")