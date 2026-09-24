---
title: "Wiki Retrieval Chatbot"
collection: talks
permalink: /talks/wikibot
level: Graduate
year: "2024"
category: exploratory
order: 5
header:
  teaser: /images/wikibot_teaser.png
teaser: /images/wikibot_teaser.png
tags: ["Information Retrieval", "BM25 / TF-IDF", "Conversational QA", "Natural Language Processing"]
affiliation: "Introduction to Information Retrieval (CSE 4/535) | University at Buffalo"
codeurl: "https://github.com/04rookie/project-3-information-retrieval"
excerpt: "Retrieval-augmented conversational agent over Wikipedia articles, combining automated web scraping, TF-IDF/BM25 inverted indexing, and conversational relevance scoring for multi-turn dialogue."
---

## Overview

This project was developed as part of *CSE 4/535 - Introduction to Information Retrieval* at the University at Buffalo. We built an end-to-end retrieval-augmented conversational agent designed to retrieve, rank, and summarize factual information from unstructured Wikipedia articles in response to conversational natural language queries.

- **Source Code**: [GitHub Repository (04rookie/project-3-information-retrieval)](https://github.com/04rookie/project-3-information-retrieval)

---

## Architecture & Pipeline

![Wiki Bot Architecture](../../images/wikibot_teaser.png)
*Figure 1: End-to-end Information Retrieval and conversational response pipeline.*

1. **Document Scraping & Normalization**: Automated scraping of multi-domain Wikipedia articles with text cleaning, stop-word elimination, and lemmatization.
2. **Inverted Indexing & Term Weighting**: Built an inverted index employing TF-IDF and BM25 relevance scoring algorithms to rank candidate document passages.
3. **Conversational QA & Dialogue Management**: Integrated a conversational scoring layer to preserve context across multi-turn queries, returning accurate factual answers with source citations.
