## Background introduction
There is an increasing emphasis on physical fitness and health in Singapore as more officer workers sign up for gym 
memberships and classes. The overall market revenue is expected to show an annual growth rate (CAGR 2019-2023) of 8.3%, 
resulting in a market volume of US$29m by 2023. In addition to that, with fitness booking platforms like GuavaPass, 
ClassPass and KFit available in Singapore, it has become more convenient to discover boutique gyms and studios, especially 
in the down town areas of Singapore for executives and office workers. This presents an excellent business opportunity 
for entrepreneurs or fitness specialists who want to start their own gym businesses in the area. However, before they go 
on to commit a huge sum of capital to start a business or gym membership, it would be wise to study and understand which l
ocations are overcrowded and which are suitable for the new business.

## Target Audience 

**Entrepreneur who is looking to open a new fitness center**: this analysis will provide an overview of the market and answers 
questions like what areas are overcrowded with competition and what areas are in need of such facilities. This will 
give our target audience a idea where could be a potential penetration point into the market.

**Investors who want to know the business opportunity in the area**: Investors can also utilize this report to 
understand the existing market landscape.

## Data sources

1.List of sub-areas in the central region of Singapore 
*source: wikipedia
2.LatLong of above areas for map plotting *source: Python geocoder package
3.Venue data: list of gym/studios in the speciied area *source: Foursquare API

## Extracting Data
We will make use of the beautifulsoup package to scrape from wikipedia. This allows us to obtain the list of sub-areas in the central region of Singapore. The central region is selected as this is where most of the office workers are. 
Next, we will use the Python geocoder package to obtain the list of corresponding latlong for the above locations. 
After that, we will utilize the search venues API from Foursquare API to get a list of 50 gyms within each sub-areas. 
The API query is using 'gym' as keyword. After obtaining the list of gyms in the region, we will their latlongs and 
get the counts of gyms within each sub-area. Finally, we use k-mean clustering to obtain 4 clusters and do visualization 
using Folium.

## Methodology 
We will obtain the list of sub-areas in the downtown of Singapore. The list is
available in the Wikipedia page (https://www.wikiwand.com/en/Planning_Areas_of_Singapore).
We will do web scraping using Python requests and beautifulsoup packages to extract the list of
areass data. 
Next We need to get the geographical coordinates in the form of latitude and longitude in order to be able to use Foursquare API. To do so, we will use the wonderful Geocoder package that will allow us to convert address into geographical
coordinates in the form of latitude and longitude. After gathering the data, we will populate the data
into a pandas DataFrame and then visualize the neighbourhoods in a map using Folium package. This
allows us to perform a sanity check to make sure that the geographical coordinates data returned by
Geocoder are correctly plotted.
Next, we will use Foursquare API to search for venues with query 'gym'.
We then make API calls to Foursquare passing in the geographical coordinates of the neighbourhoods in a Python loop. Foursquare will return the venue data in JSON
format and we will extract the venue name, venue category, venue latitude and longitude. With the
data, we can check how many gyms were returned for each area. Then, we will analyse each
area by grouping the rows by neighbourhood. By doing so, we are also preparing the data for use in clustering.
Lastly, we will perform clustering on the data by using k-means clustering. We will cluster the area into 4 clusters based on the number of . The results will allow us to identify which area have higher
concentration of gyms while which have fewer. 

## Results 
![cluster result](https://github.com/zhoukai07/Coursera_Capstone/blob/master/Screenshot%202019-08-27%20at%2022.56.42.png)

There are 4 clusters based on the number of gyms in the area: 
1. Cluster 0 (in red): Little number of gyms, range from 3-6
2. Cluster 1 (in Purple): 2nd Most number of gyms, range from 13-17
3. Cluster 2 (in Cyan): Moderate number of gyms range from 8-12
4. Cluster 3 (in Orange): Most number of gyms, 29

## Discussion
The visualization fits the intuition that the number of gyms starts to decrease as the area gets further away from the downtown area. There are 4 areas (in red), despite their close proximity to the downtown, have little number of gyms. This seems indicate potentially other factors preventing existing owners to set up business over there.
Orchard, being the most popular shopping district and working area, has the higher number of gyms available. 


## Conclusions
In this project, we have gone through the process of identifying the business problem, specifying the
data required, extracting and preparing the data, performing machine learning by clustering the data
into 3 clusters based on their similarities, and lastly providing recommendations to the relevant
stakeholder. That being said, there are other factors such as rental, nearby facilities that could impact the accessibility and hence viability of opening a gym in the area. We should look into these factors as well. 
