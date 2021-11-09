# Overview

Classification model for expected goals (xG) in women's club soccer, predicting the likelihood that a shot will score using data extracted from StatsBomb.


## Expected Goals (xG)

xG is used to indicate the quality of a shot.

xG, as a metric, measures the likelihood that a shot will result in a goal based on the characteristics of the shot and the play preceding the shot.

xG is measured on a scale between zero and one, with one representing a goal. For example, a shot with a 0.5 xG indicates a shot having a 50% chance of being a goal.

[What is xG?](https://medium.com/@wswager/what-is-xg-f6f82053d2cc)


## Classification Model

The metric of expected goals is calculated through the use of a classification model.

A classification model refers to a predictive modeling problem where a class label is predicted for a given example of input data.

For this project a supervised approach was used with the training data for the model including which shots were goals.


## Data Extraction


    'Data extraction is the act or process of retrieving data out of…data sources for further data processing'

_[Wikipedia](https://en.wikipedia.org/wiki/Data_extraction)_


## The Data

The data for this project was extracted from[ StatsBomb](https://statsbomb.com/)’s Open Data.

StatsBomb are a United Kingdom based football (soccer) data analytics company. StatsBomb provide free access to a segment of their proprietary dataset via GitHub:[ StatsBomb Open Data](https://github.com/statsbomb/open-data)


![alt_text](images/image1.jpg "image_tooltip")


StatsBomb Open Data is organized in JSON files:

**Matches**



* Folders are organized by competition (league or tournament)
* Files within the folders are organized by season (year) ID
* Files contain nested dictionaries with descriptive data for each individual match

**Events**



* Files organized by match ID
* Files contain nested dictionaries with descriptive data for each event within each individual match

For the purposes of this project the relevant data targeted was, primarily, characteristics of shots and, secondarily, characteristics of the plays creating those shots, from women’s club soccer matches.

_Note: Assessment of plays creating shots is subjective and based on domain knowledge specific to the sport of soccer_


## Notebook Index



1. [Data Extraction](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
2. [Data Cleaning](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
3. [Features Engineering](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
4. [Data Exploration](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
5. [Data Preprocessing](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
6. [Prediction Modeling](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)
7. [Conclusions](https://colab.research.google.com/drive/1VIuv4Bi7LLvt307fPfxoapGf-kKA4PES#scrollTo=yxgRJvr2sggW)


## Results

_READ ME Coming Soon_
