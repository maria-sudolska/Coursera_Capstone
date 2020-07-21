# New York City Neighborhood Suitability for a Business Plan: 
# Healthy Food Store
## Applied Data Science Capstone Project at Coursera

## Introduction
In this project, I'm analyzing New York City neighborhood and Foursquare data to find a suitable place to start a store with healthy food. The goal is to identify the best neighborhoods, using K-Means clustering, where such store could profit. Following assumptions are taken:
- People with an active lifestyle would be the ones who could benefit from a store with healthy food. These people most likely use facilities like gyms, pools, other sport facilities or parks.
- Candidate neighborhoods shouldn't be rich in facilities like supermarkets and groceries, that could also sell healthy food and lure our customers away from the new shop.
- Candidate neighborhoods shouldn’t have many restaurants of different kinds, fast food, pizza since these are indicators of social and cultural life, not sport activities at all.
- Neighborhood clustering based on abundance of venues of different categories enables decisions whether the neighborhood is a good candidate or not.

To put it simple, I want to group the neighborhoods according to typical venue categories, and identify those neighborhoods that fulfill above conditions. 

## Data
Data from two sources are combined:
- [New York City neighborhood data](https://geo.nyu.edu/catalog/nyu_2451_34572) containing following information about every neighborhood:
  - neighborhood name
  - borough name
  - neighborhood latitude
  - neighborhood longitude
- location data from [Foursquare](https://foursquare.com/) API that include information about venues and their categories in a neighborhood

## Methods
I used standard K-Means clustering to cluster neighborhoods based on their similarities measured in terms of different venue categories and their abundance in a neighborhood to:
- cluster all neighborhoods in New York City with K=5 and K=10
- cluster neighborhoods within each borough with K=5 and K=8

I compared the results afterwards. The goal of this approach was to find a reasonable way to cluster neighborhoods, determine the similarity of neighborhoods within boroughs and among boroughs, and recommend proper candidate neighborhoods to start a healthy food store

## Findings
Taking all neighborhoods for clustering (irrespective of the borough division) offered a high-level overview of the neighborhoods. With both K=5 and K=10, the most of neighborhoods were part of one big cluster characterized by the most frequent venue categories in NYC. Although higher K helped to reveal some relevant candidates, the better approach was to cluster neighborhoods within boroughs.  

Cluster analysis of neighborhoods within boroughs revealed more useful insights. The largest clusters within each borough were similar and included venues like restaurants, pizza places, sandwich places, and coffee shops/cafes. I didn't identify a big neighborhood cluster of the type sport/leisure time. However, there are some smaller clusters and individual neighborhoods (technically, clusters containing only one member) that do not fall under the common category "Restaurant/Pizza/Coffee". These could be identified as appropriate candidates to open a healthy food store.

## Project Structure
The project contains following files and directories:
- [nyc-healthy-food-store.ipynb](nyc-healthy-food-store.ipynb) - Jupyter notebook containing all the code from data gathering to clustering
- [nyc-healthy-food-store-report.pdf](nyc-healthy-food-store-report.pdf) - report describing all the efforts to gather, assess, clean, explore, and cluster the data
- [nyc-healthy-food-store-presentation.pdf](nyc-healthy-food-store-presentation.pdf) - project presentation
- [data](data) - folder contains the exported GeoJSON file from [NYU Spatial Data Repository](https://geo.nyu.edu/catalog/nyu_2451_34572)
- [figures](figures) - folder contains generated figures (in jpg format) that were used in the report and presentation
