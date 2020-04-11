---
title: 'Topic Modeling on CORD-19 articles'
tags:
  - topic modeling
  - covid-19
  - cord-19
  - lda
authors:
  - name: Thanasis Vergoulis
    orcid: 0000-0003-0555-4128
    affiliation: 1
  - name: Panagiotis Deligiannis
    orcid: 0000-0001-7163-6039
    affiliation: 2
  - name: Serafeim Chatzopoulos
    orcid: 0000-0003-1714-5225
    affiliation: 1
  - name: Ali Haider Bangash
    orcid: 0000-0002-8256-3194
    affiliation: 3
  - name: Ilias Kanellos
    orcid: 0000-0003-2146-3795
    affiliation: 1
  - name: Danae Pla Karidi
    orcid: 0000-0002-3154-6212
    affiliation: 1
affiliations:
 - name: ATHENA RC, Maroussi, Greece
   index: 1
 - name: University of the Peloponnese, Tripoli, Greece
   index: 2
- name: Shifa College of Medicine, STMU, Islamabad, Pakistan
   index: 3
bibliography: paper.bib
---

# Introduction

Since the beginning of the 2019-20 coronavirus pandemic, many scientific articles studying the COVID-19 disease and the coronavirus that causes it have been published. In addition, a large number of previously published articles, that describe useful, relevant background knowledge became popular. 

In response to this situation, the Allen Institute for AI constructed and made available the COVID-19 Open Research Dataset (CORD-19) [@CORD-19], a dataset containing metadata for over 47,000 articles which are relevant to COVID-19 and the coronavirus family of viruses. This dataset also includes the full text of over 36,000 of these articles. The intention was to mobilize researchers to analyse these data using contemporary techniques of text mining and natural language processing to generate insights in support of the fight against the corresponding disease. 

Based on the previous, and in the context of the [COVID-19 Biohackathon of April 2020](https://github.com/virtual-biohackathons/covid-19-bh20), we decided to analyse the CORD-19 dataset applying LDA [@LDA], a widely known topic modeling algorithm, to reveal a set of topics that are relevant to the corresponding texts. Our intention was to identify potentially interesting, latend topics and relationships that could help researchers better understand the domain and better organise their knowledge about it. As a result, we worked in the following tasks:

* We collected and preprocessed data from the CORD-19 dataset.  
* We applied LDA on the abstracts of the articles contained in the CORD-19 dataset.
* We developed a prototype interface to visualise the produced topics. 
* We performed a first attempt to interpret and evaluate the resulting topics.  

# Methods

## Data Collection 

We have collected the abstracts for xxx articles contained in the CORD-19 [@CORD-19] dataset. These abstracts have been extracted from the corresponding metadata file provided by the dataset. We used this set to create two collection: the one containing all the articles, and a another one that contains only articles published in 2020. Our intention was to produce topics based on both collection. The former collection is expected to provide more general topics reflecting not only research focus on the current coronavirus outbreak but also research on relevant areas. The latter collection is expected to produced more focused topics, tailored for the current disease, its relevant coronavirus, and the corresponding outbreak. 

We also have collected (for future use) all full texts of articles provided by CORD-19 and the tweets of one day (March 12th, 2020) from the COVID-19-TweetIDs dataset [@covid-19-tweetids]. 

## Topic Modeling

In order to extract the latent topics from the scientific articles we generated two corpora of abstracts which are provided by the CORD-19 dataset. The first corpus consisted of all the available English abstracts provided by CORD-19. The second corpus, which was a subset of the first, consisted only of English abstracts of scientific articles published in 2020. We used language detection to classify the English texts and rule out other languages, so that any prospective produced topics will not be affected (using a multilingual training corpus for the topic model, can lead to language specific topics that may not carry any particular semantic clarity).

Each text of the filtered datasets is passed through a preprocessing module that removes textual noise, normalizes the vocabulary and converts the text to more machine-readable form. Initially we use a part-of-speech tagger to detect terms that are nouns, adjectives and verbs and lemmatize them. We then proceed by decapitalizing the text and removing terms that are stopwords, based on a defined stopword list. Punctuation is also removed with the exception of hyphens ("-") and slashes ("/"). We retain these notations as we've observed that are being widely used in our dataset for biological and medical notation. The resulting texts are then accepted only if they have more than 5 terms, after the preprocessing.

Produced preprocess texts are accumulated in a preprocessed text corpus and all terms that are being used in the corpus are being recorded, creating a dictionary. The dictionary maps each term to its number of occurences in the corpus and the number of documents the term appears in, thus providing a metric of significance and redundancy of each term. Terms with too few document occurences can be considered insignificant while ones that appear accross most of the documents can be considered as a stopword. This allows to limit the dictionary to terms that satisfy certain statistical conditions. Since our training dataset can be considered as not sufficient for topic modeling, we limit our dictionaries based on the filters described below, ordered by significance:

1. Keep the terms "coronavirus","sars-cov-2","covid-19" and "sars-ncov2"
2. Discard any term that appears in less than 2 documents
3. Discard any term that appears in more than 6% of the documents
4. Keep at most 30000 terms

## Prototype Interface

A prototype Web interface to demonstrate the produced topics has been developed using PHP, CSS, Javascript, and HTML. The interface is comprised of two basic pages. The first visualises the topics produced based on all the collected CORD-19 abstracts, while the second presents the topics based only on the abstracts of the 2020 articles (i.e., those that were published after the beginning of the outbreak). For both pages, only the best performing models (acccording to our initial evaluation and interpretation) are visualised. As a result, for the case of all articles, we used the model having 50 topics XXX, while for the case of 2020 articles we used the model XXX. 

# Discussion 

TODO: ALI ADD CONTENT HERE! 

# Future work

We plan to extend this work in the future in the following ways:

* We plan to train more topic models, using extra COVID-19-related text. For example, we plan to apply LDA on the available full-texts of CORD-19 dataset or on corpora of relevant tweets (e.g., [@covid-19-tweetids]). 
* We plan to examine alternative topic modeling algorithms like hLDA [@hLDA] and LSA [@LSA] and to evaluate the quality of their results in comparison to the LDA results. 
* We plan to extend the developed prototype to provide more useful features that can help scientists to generate useful insights about COVID-19 and relavenat issues. 

# Code and Data availability

A Github repository containing all relevant codes and data can be found here:

* [Cord19-topics Github page](https://github.com/vergoulis/cord19-topics)

# Acknowledgements
This work was done within the [COVID-19 Biohackathon of April 2020](https://github.com/virtual-biohackathons/covid-19-bh20).

# References

Leave thise section blank, create a paper.bib with all your references.
