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
    orcid: 0000-0000-0000-0000
    affiliation: 2
  - name: Serafeim Chatzopoulos
    orcid: 0000-0003-1714-5225
    affiliation: 1
  - name: Ilias Kanellos
    orcid: 0000-0003-2146-3795
    affiliation: 1
  - name: Ali Haider Bangash
    orcid: 0000-0002-8256-3194
    affiliation: 3
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

Based on the previous, and in the context of the [COVID-19 Biohackathon of April 2020](https://github.com/virtual-biohackathons/covid-19-bh20), we decided to analyse the CORD-19 dataset applying LDA [@LDA], a widely known topic modeling algorithm, to reveal a set of topics that are relevant to the corresponding texts. Our intention was to identify potentially interesting, latend topics and relationships that could help researchers better understand and organise their knowledge of the domain. As a result, we worked in the following tasks:

* We collected and preprocessed data from the CORD-19 dataset.  
* We applied LDA on the abstracts of the articles contained in the CORD-19 dataset.
* We developed a prototype interface to visualise the produced topics. 
* We performed a first attempt to interpret and evaluate the resulting topics.  

# Methods

## Data Collection 

TODO 

## Topic Modeling

TODO

## Prototype Interface

TODO

# Discussion 

TODO 

# Future work

TODO

# Jupyter notebooks, GitHub repositories and data repositories

* Please add a list here
* Make sure you let us know which of these correspond to Jupyter notebooks. Although not supported yet, we plan to add features for them
* And remember, software and data need a license for them to be used by others, no license means no clear rules so nobody could legally use a non-licensed research object, whatever that object is

# Acknowledgements
This work was done within the [COVID-19 Biohackathon of April 2020](https://github.com/virtual-biohackathons/covid-19-bh20).

# References

Leave thise section blank, create a paper.bib with all your references.
