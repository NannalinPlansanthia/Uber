# Uber
New York City is a premier destination during holiday season. As festivities span from Fifth Avenue to Central Park, rideshare platforms become essential for traveling within and across boroughs. This report utilizes K-means clustering to segment Uber's customer during the 2023 Christmas period.
## Overview
1. Data Pre-processing
2. Exploratory Data Analysis
3. K-means Clustering
4. Cluster Analysis

## Data
This dataset is available on NYC Open Data <https://data.cityofnewyork.us/Transportation/2023-High-Volume-FHV-Trip-Data/u253-aew4/about_data>
These records are generated from the trip record submissions made by High Volume For-Hire Vehicle (FHV) bases. Each row represents a single trip in a FHV dispatched by a high volume base. The trip records include fields capturing the high volume license number, the pickup and drop-off date, time, and taxi zone location ID, which correspond with the NYC Taxi Zones open dataset.
|Column Name|Column Description| 
|:--------:|:--------:|
|hvfhs_license_num	|The TLC license number of the HVFHS base or business|
|dispatching_base_num	|The TLC Base License Number of the base that dispatched the trip|
|originating_base_num |base number of the base that received the original trip request|
|request_datetime|	date/time when passenger requested to be picked up|
|on_scene_datetime|	date/time when driver arrived at the pick-up location (Accessible Vehicles-only)|
|pickup_datetime|	The date and time of the trip pick-up|
|dropoff_datetime|	The date and time of the trip drop-off|
|PULocationID|	TLC Taxi Zone in which the trip began|
|DOLocationID|	TLC Taxi Zone in which the trip ended|
|trip_miles|	total miles for passenger trip|
|trip_time|	total time in seconds for passenger trip|
|base_passenger_fare|	base passenger fare before tolls, tips, taxes, and fees|
|tolls|	total amount of all tolls paid in trip|
|bcf|	total amount collected in trip for Black Car Fund|
|sales_tax|	total amount collected in trip for NYS sales tax|
|congestion_surcharge|	total amount collected in trip for NYS congestion surcharge|
|airport_fee|	$2.50 for both drop off and pick up at LaGuardia, Newark, and John F. Kennedy airports|
|tips|	total amount of tips received from passenger|
|driver_pay|	total driver pay (not including tolls or tips and net of commission, surcharges, or taxes)|
|shared_request_flag|	Did the passenger agree to a shared/pooled ride, regardless of whether they were matched? |
|shared_match_flag|	Did the passenger share the vehicle with another passenger who booked separately at any point during the trip?|
|access_a_ride_flag|	Was the trip administered on behalf of the Metropolitan Transportation Authority (MTA)? |
|wav_request_flag|	Did the passenger request a wheelchair-accessible vehicle (WAV)?|
|wav_match_flag|	Did the trip occur in a wheelchair-accessible vehicle (WAV)? |

access more information through this link <https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page>
## Results
- Pickup volume was highest at JFK Airport, followed by Crown Heights North, LaGuardia Airport, East Flatbush/Remsen Village, and Jackson Heights. These areas represent airport and residential zones where population volume and global flight schedules create high demand for for-hire vehicles.
- Outside NYC represents the primary drop-off location, with JFK Airport, LaGuardia Airport, Crown Heights North, and East New York following as the top intra-city locations.

<img width="1096" height="658" alt="image" src="https://github.com/user-attachments/assets/dae2e9c2-e2a5-4878-9551-2a2407b263d0" />

<img width="1083" height="664" alt="image" src="https://github.com/user-attachments/assets/081f488a-f76c-4370-9e29-41ca5fe9e925" />
Uber customers can be segmented into four distinct clusters based on time-of-day patterns: <br>

1. Cluster 0 – Night commuters (approximately 9:00 PM to 5:00 AM) <br>
2. Cluster 1 – Midday commuters (approximately 11:00 AM to 3:00 PM) <br>
It exhibits the highest average base passenger fare at approximately USD 26.94.
3. Cluster 2 – Evening commuters (approximately 4:00 PM to 8:00 PM) <br>
Trips in this cluster are concentrated during evening peak hours of NYC. This is the largest segment, representing 90,051 trips. Moreover, trips exhibit the highest average duration, with average times of 19 minutes.
4. Cluster 3 – Morning commuters (approximately 6:00 AM to 10:00 AM) <br>
This is the smallest segment, accounting for 36,264 trips. This cluster exhibits the highest ratio of airport trips, at roughly 15 percent.

The four clusters share the following common characteristics:
1. The average trip distance is approximately 6 miles.
2. A congestion surcharge is applied in about 30 percent of trips.
3. Almost every trips are individual rides.

## References
1. NYC Open Data. (2024).  2023 High Volume FHV Trip Data.  Retrieved December 30, 2025, from <https://data.cityofnewyork.us/Transportation/2023-High-Volume-FHV-Trip-Data/u253-aew4/about_data>
2. NYC Taxi & Limousine Commission. (n.d.).  TLC Trip Record Data. Retrieved December 30, 2025, from <https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page>
3. scikit-learn.  (n.d.).  Selecting the number of clusters with silhouette analysis on KMeans clustering.  Retrieved January 7, 2026, from <https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html>    


