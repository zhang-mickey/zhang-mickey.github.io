---
layout: post
title: "Entity linking wiki"
date:   2023-11-30
tags: [nlp]
comments: false
author: zhang
---
# wiki
The structure of Wikipedia provides a set of useful features for generating candidate entities, such as entity pages,redirect pages,disambiguation pages,bold phrases from the first paragraphs.
# Candidate entity generation
approaches to candidate entity generation are mainly based on `string comparison` between the entity mention and the name of the entity existing in a knowledge base.
main approaches
- Name Dictionary based tech
- Based on Search engine
submit the entity mention together with its short context to the Google API and obtained only Web pages within Wikipedia to regard them as candidate entities.
# Candidate entity ranking
