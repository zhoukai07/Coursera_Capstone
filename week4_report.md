# Week 4 Problem Description and Approach

## A description of the problem and a discussion of the background. (15 marks)

### background introduction 

The fitness industry in Singapore is booming with increasing awareness of **healthy-living lifestyle**. The overall market revenue is expected to show an annual growth rate (CAGR 2019-2023) of 8.3%, resulting in a market volume of US$29m by 2023.
In addition, with fitness booking platforms like GuavaPass, ClassPass and KFit available in Singapore, it has become more convenient to discover boutique gyms and studios, especially in the [central regions](https://www.wikiwand.com/en/Planning_Areas_of_Singapore) for executives and office workers. 
This does not only present an excellent business opportunities for entrepreneurs or fitness specialists who want to build their own businesses in the area, consumers in these regions are also exposed to variety of gyms and studios.
However, before they go on to commit a huge sum of capital to start a business or gym membership, it would be ideal to study and understand the current landscape of market within the region.

### User problems  

1. As a fitness instructor who is looking to open my own fitness centre central region of Singapore, I want to understand what types of gyms and fitness centres are already available in the area and possible locations to start my business. 

2. As a worker and fitness enthusiast who is looking for available gym classes in the region, I want to know what are the popular gyms and studios in the area. 



## A description of the data and how it will be used to solve the problem. (15 marks)

### Data sources 

1. List of sub-areas in the central region of Singapore 
  *source: [wikipedia](https://www.wikiwand.com/en/Planning_Areas_of_Singapore)
2. LatLong of above areas for map plotting
  *source: Python geocoder package
3. Venue data: list of gym/studios in the speciied area 
  *source: Foursquare API


### Proposed approach

We will use the web scraping technique learned in the course to obtain list of areas in centra region of Singapore. This can be done using the beautifulsoup package. 
Next, we will use the Python geocoder package to obtain the list of latlong for above locations.
We will explore Foursquare API, using get, search venues(using keyword 'gym') data etc to get the relevant information. 
