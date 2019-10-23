---
layout: post
title:  "TrashSnapp: An Awesome Mobile App for Waste Sorting"
date:   2019-10-22
img:
description:
permalink: /TrashSnapp
#categories: jekyll updat
---
## Introduction
![waste](https://advds71x.github.io/DataSprint/img/waste-sorting.jpg)

[Image Source](https://www.vectorstock.com/royalty-free-vector/waste-sorting-recycling-flat-banners-set-vector-9586056)

* Target audience:
The general public who needs help with trash sorting
* Sustain:
  - Send messages to the users to keep them engaged with the app and enable users to frequently and easily update apps
  - Market to grow new users
  - Track the app with analytics
* Failure:
  - Not applicable to non smartphone users
  - Require a clean background when scanning the trash
* Budget (3-5 month) ($18000)
  - Business Analysis ($3000)
  - Data storage/hosting app on servers($2000)
  - App development agent on the features: camera ($1000), access to the gallery($600), internet connection ($600), data collection ($700), offline capabilities ($3500), search ($600), adds($700), data encryption ($1000)
  - App release (Google App Play: $25, Apple Store: $99)
  - App maintenance ($2000)



## User Interface
![ui](https://advds71x.github.io/DataSprint/img/TrashSnapp.PNG)

* Once you scan the trash, you will know the categories of the trash.
* We also provide the typewriting search of the trash categories as an alternative to the image uploading


## Server Design
### Data Collection
  - Trash images and categories manually collected by [Gary Thung and Mindy Yang](https://github.com/garythung/trashnet). THe dataset currently includes 2527 images and 6 trash classes, about 500 images in each category.  
  - Web Crawling and Scraping from Google images
  - Crowdsourcing


### Image Data Analysis using R package `imager`
```
library(imager)
library(ggplot2)
library(gridExtra)
par(mfrow=c(2,2))
p1 = plot(glass)
p2 = plot(grayscale(glass))
p3 = plot(glass/2,rescale = F)
p4 = plot(glass,colorscale = cscale,rescale = F)
```
![glass_panels](https://advds71x.github.io/DataSprint/img/glass-panels.jpg)


### Classification Algorithm
we will train a deep learning model similar to [VGGNet](https://arxiv.org/pdf/1409.1556.pdf) but fewer layers, based on the labeled trash image data.

 - Workflow Demo

![demo_nnet](https://advds71x.github.io/DataSprint/img/demo_nnet.png)

- Network Architecture

<!--
| Input     |
| ----------- |
| 3 &times; 3 Conv, 64  |
| 3 &times; 3 Conv, 64  |
| 2 &times; 2 Pool  |
| 3 &times; 3 Conv, 64  |
| 3 &times; 3 Conv, 64  |
| 2 &times; 2 Pool  |
| FC1  |
| FC2  |
| Softmax  |
-->

![demo_nnet](https://advds71x.github.io/DataSprint/img/arch.PNG)
