# Week 4 Problem Description and Approach

## A description of the problem and a discussion of the background. (15 marks)

### Background introduction 

There is an increasing emphasis on physical fitness and health in Singapore as more officer workers sign up for gym memberships and classes. The overall market revenue is expected to show an annual growth rate (CAGR 2019-2023) of 8.3%, resulting in a market volume of US$29m by 2023.
In addition to that, with fitness booking platforms like GuavaPass, ClassPass and KFit available in Singapore, it has become more convenient to discover boutique gyms and studios, especially in the down town areas of Singapore for executives and office workers. This presents an excellent business opportunity for entrepreneurs or fitness specialists who want to start their own gym businesses in the area. 
However, before they go on to commit a huge sum of capital to start a business or gym membership, it would be wise to study and understand which locations are overcrowded and which are suitable for the new business. 

### Target Audience  

1. **Entrepreneur who is looking to open a new fitness center**: this analysis will provide an overview of the market and answers questions like what areas are overcrowded with competition and what areas are in need of such facilities. This will give our target audience a idea where could be a potential penetration point into the market. 

2. **Investors who want to know the business opportunity in the area**: Investors can also utilize this report to understand the existing market landscape.  



## A description of the data and how it will be used to solve the problem. (15 marks)

### Data sources 

1. List of sub-areas in the central region of Singapore 
  *source: [wikipedia](https://www.wikiwand.com/en/Planning_Areas_of_Singapore)
2. LatLong of above areas for map plotting
  *source: Python geocoder package
3. Venue data: list of gym/studios in the speciied area 
  *source: Foursquare API
 

### Extracting data

We will make use of the beautifulsoup package to scrape from [wikipedia](https://www.wikiwand.com/en/Planning_Areas_of_Singapore). This allows us to obtain the list of sub-areas in the central region of Singapore. The central region is selected as this is where most of the office workers are. Next, we will use the Python geocoder package to obtain the list of corresponding latlong for the above locations.
After that, we will utilize the search venues API from Foursquare API to get a list of 50 gyms within each sub-areas. The API query is using 'gym' as keyword. After obtaining the list of gyms in the region, we will their latlongs and get the counts of gyms within each sub-area. Finally, we use k-mean clustering to obtain 4 clusters and do visualization using Folium.  
