# AirBnB MongoDB Analysis
## Data
### Data set details
The data set is about the information of AirBnB in Hong Kong and it comes from [Inside Airbnb website](https://insideairbnb.com/). The original data format is: [listings.csv.gz](https://data.insideairbnb.com/china/hk/hong-kong/2023-12-20/data/listings.csv.gz)
### Display raw data
Here is the first 5 rows of the row data. (I clip some text.)
| id     | listing_url                            | scrape_id    | last_scraped | source       | name                                                          | description                                                                                                                                                           | neighborhood_overview                                              | picture_url                                                             | host_id | host_url                            | host_name | host_since | host_location     | host_about                                                                                                                                                                                                                                        | host_response_time | host_response_rate | host_acceptance_rate | host_is_superhost | host_thumbnail_url                                                    | host_picture_url                                                       | host_neighbourhood | host_listings_count | host_total_listings_count | host_verifications        | host_has_profile_pic | host_identity_verified | neighbourhood | neighbourhood_cleansed | neighbourhood_group_cleansed | latitude | longitude | property_type       | room_type     | accommodates | bathrooms | bathrooms_text | bedrooms | beds | amenities                                                       | price     | minimum_nights | maximum_nights | minimum_minimum_nights | maximum_minimum_nights | minimum_maximum_nights | maximum_maximum_nights | minimum_nights_avg_ntm | maximum_nights_avg_ntm | calendar_updated | has_availability | availability_30 | availability_60 | availability_90 | availability_365 | calendar_last_scraped | number_of_reviews | number_of_reviews_ltm | number_of_reviews_l30d | first_review | last_review | review_scores_rating | review_scores_accuracy | review_scores_cleanliness | review_scores_checkin | review_scores_communication | review_scores_location | review_scores_value | license | instant_bookable | calculated_host_listings_count | calculated_host_listings_count_entire_homes | calculated_host_listings_count_private_rooms | calculated_host_listings_count_shared_rooms | reviews_per_month |
|--------|----------------------------------------|--------------|--------------|--------------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------------|---------|-------------------------------------|-----------|------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|--------------------|----------------------|--------------------|----------------------------------------------------------------------|------------------------------------------------------------------------|--------------------|----------------------|--------------------------|---------------------------|---------------------|------------------------|---------------|-----------------------|-----------------------------|----------|-----------|--------------------|---------------|--------------|-----------|----------------|----------|------|-----------------------------------------------------------------|-----------|----------------|----------------|------------------------|------------------------|------------------------|------------------------|------------------------|---------------------|------------------|-----------------|-----------------|-----------------|-----------------|------------------------|--------------------|------------------------|------------------------|--------------|-------------|-----------------|-----------------|-----------------|-----------------|------------------------|-------------------|------------------------|------------------------|--------------|-------------|----------------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------|
| 17891  | https://www.airbnb.com/rooms/17891     | 2.02312E+13  | 12/21/2023   | previous scrape | Rental unit in Hong Kong Island · ★4.76 · Studio · 1 bed · 1 bath |  |Best neighborhood in Hong Kong! A mix of old and new.                                                                                                                  | https://a0.muscache.com/pictures/119686/6ced58c4_original.jpg  | 69063  | https://www.airbnb.com/users/show/69063 | Candace   | 1/9/2010   | Los Angeles, CA   | Hi, my name is Candace Campos...  | N/A                | N/A                | N/A                  | f                  | https://a0.muscache.com/im/pictures/user/b439cf98-b81c-4555-bb1c-384cf45fe320.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/pictures/user/b439cf98-b81c-4555-bb1c-384cf45fe320.jpg?aki_policy=profile_x_medium  | Sheung Wan         | 1                    | 2                        | ['phone', 'work_email'] | t                   | t                      | Hong Kong Island | Central & Western     |                           | 22.28327 | 114.14988 | Entire rental unit | Entire home/apt | 3            |           | 1 bath         |        |  1     | []                                                              |         |     60           |            365    | 60                      | 60                      | 365                     | 365                     | 60                      | 365                  |              |               | 0               | 0               | 0          |0     | 12/21/2023             | 73                 | 0                      | 0                      | 4/23/2010    | 11/29/2017  | 4.76                 | 4.73                   | 4.51                      | 4.92                   | 4.93                          | 4.9                    | 4.66               |          | f               | 1                              | 1                                        | 0                                      | 0                                        | 0.44               |
| 72571  | https://www.airbnb.com/rooms/72571     | 2.02312E+13  | 12/20/2023   | city scrape   | Rental unit in Sheung Wan · ★4.22 · Studio · 1 bed · 1 bath     |         |                                                                                                                                                              | https://a0.muscache.com/pictures/2849554/d226294d_original.jpg  | 304876 | https://www.airbnb.com/users/show/304876 | Brendan   | 11/30/2010 | Hong Kong         | I was born in California and raised in Hong Kong... | within an hour      | 100%               | 99%                  | f                  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium  | Sheung Wan         | 10                   | 58                       | ['email', 'phone']        | t                   | t                      |               | Central & Western     |                           | 22.28463 | 114.15054 | Entire rental unit | Entire home/apt | 2            |           | 1 bath         |          |   1   | []                                                              | $482.00   | 28             | 1125           | 28                     | 28                     | 1125                     | 1125                     | 28                     | 1125                 |            | t              | 0              | 0              | 0|0              | 12/20/2023             | 151                | 0                      | 0                      | 2/26/2011    | 3/11/2022   | 4.22                 | 4.04                   | 4.55                      | 4.43                   | 4.51                          | 4.73                   | 4.13               |          | f               | 9                              | 5                                        | 4                                        | 0                                        | 0.97               |
| 132773 | https://www.airbnb.com/rooms/132773    | 2.02312E+13  | 12/21/2023   | city scrape   | Rental unit in Hong Kong Island · ★4.52 · 2 bedrooms · 3 beds · 1 bath | |The Sheung Wan neighbourhood is ever changing and a fantastic mix of "old' and "new" Hong Kong... | https://a0.muscache.com/pictures/36936441/e4c1f31d_original.jpg | 304876 | https://www.airbnb.com/users/show/304876 | Brendan   | 11/30/2010 | Hong Kong         | I was born in California and raised in Hong Kong... | within an hour      | 100%               | 99%                  | f                  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium  | Sheung Wan         | 10                   | 58                       | ['email', 'phone']        | t                   | t                      | Hong Kong Island | Central & Western     |                           | 22.28921 | 114.14325 | Entire rental unit | Entire home/apt | 6            |           | 1 bath         |         |  3    | []                                                              | $1,475.00 | 5              | 365            | 5                      | 5                      | 365                      | 365                      | 5                      | 365                   |                 | t              | 0               | 0               | 0|0               | 12/21/2023             | 247                | 24                     | 3                      | 7/19/2011    | 12/3/2023   | 4.52                 | 4.49                   | 4.7                       | 4.6                    | 4.67                          | 4.43                   | 4.41               |          | f               | 9                              | 5                                        | 4                                        | 0                                        | 1.63               |
| 163664 | https://www.airbnb.com/rooms/163664    | 2.02312E+13  | 12/20/2023   | city scrape   | Rental unit in Sheung Wan · ★4.28 · 2 bedrooms · 3 beds · 1 bath | |Fantastic traditional Hong Kong neighborhood with lots of history at every street alley and corner...                                                          | https://a0.muscache.com/pictures/15184030/8d06b40b_original.jpg | 304876 | https://www.airbnb.com/users/show/304876 | Brendan   | 11/30/2010 | Hong Kong         | I was born in California and raised in Hong Kong...| within an hour      | 100%               | 99%                  | f                  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium  | Sheung Wan         | 10                   | 58                       | ['email', 'phone']        | t                   | t                      | Sheung Wan      | Central & Western     |                           | 22.28494 | 114.14901 | Entire rental unit | Entire home/apt | 6            |           | 1 bath         |         |    3  | []                                                              | $616.00   | 2              | 365            | 2                      | 2                      | 365                      | 365                      | 2                      | 365                   |                | t              | 0               | 0              | 0|0               | 12/20/2023             | 225                | 0                      | 0                      | 8/25/2011    | 2/16/2021   | 4.28                 | 4.24                   | 4.41                      | 4.44                   | 4.58                          | 4.68                   | 4.31               |          | f               | 9                              | 5                                        | 4                                        | 0                                        | 1.5                |
| 163742 | https://www.airbnb.com/rooms/163742    | 2.02312E+13  | 12/21/2023   | city scrape   | Rental unit in Sheung Wan · ★4.35 · 2 bedrooms · 3 beds · 1 bath | |Fantastic traditional Hong Kong neighborhood with lots of history at every street alley and corner...                                   | https://a0.muscache.com/pictures/15195137/ff7e10d7_original.jpg | 304876 | https://www.airbnb.com/users/show/304876 | Brendan   | 11/30/2010 | Hong Kong         | I was born in California and raised in Hong Kong...| within an hour      | 100%               | 99%                  | f                  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small  | https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium  | Sheung Wan         | 10                   | 58                       | ['email', 'phone']        | t                   | t                      | Sheung Wan      | Central & Western     |                           | 22.28657 | 114.14889 | Entire rental unit | Entire home/apt | 6            |           | 1 bath         |         |  3    | []                                                              | $1,210.00 | 4              | 365            | 4                      | 4                      | 365                     | 365                      | 4                      | 365                   |                 |   t             | 0       |0        | 0               | 0               | 12/21/2023             | 244                | 10                     | 0                      | 8/11/2011    | 11/20/2023  | 4.35                 | 4.26                   | 4.51                      | 4.52                   | 4.59                          | 4.62                   | 4.31               |          | f               | 9                              | 5                                        | 4                                        | 0                                        | 1.62               |

### Data srubbing

1. I found that there are some columns where every id has the same value. **I removed all these columns.** For example, the column: bathrooms. I used `SUM` function in spreasheet and I found there are no values in this column for all id's. So I decided to delete the column. Same for bedrooms column. Additinally, I found the columns: amentities, calendar_updated, description, neighbourhood_group_cleansed, and license are same as bathrooms and bedrooms cloumns, so I deleted all of them.
2. I found there are some missing values. **I used Python to delete all rows which have missing values in vital information: price, host_id, and name.** I leave other missing values, this information can be get by using the information we already had like cotacting host.
Here is my code:
```
import pandas as pd
# Load the newly uploaded CSV file into a DataFrame
new_file_path = '/Users/apple/Desktop/listings_clean.csv'
data_scrubbing = pd.read_csv(new_file_path)

# Remove rows where critical columns have missing values
critical_columns = ['host_id', 'name', 'price']
data_scrubbing = data_scrubbing.dropna(subset=critical_columns)

# export the csv.file as listings_clean.csv
output_file_path = '/Users/apple/Desktop/listings_clean.csv'

data_scrubbing.to_csv(output_file_path, index=False)

```
## Analysis
1. Show exactly two documents from the listings collection in any order. Here is the code
```
db.listings.find().limit(2)
```
Here is the result:
```

[
  {
    _id: ObjectId('660deed0b6515eb205792dfd'),
    id: 72571,
    listing_url: 'https://www.airbnb.com/rooms/72571',
    scrape_id: 20231200000000,
    last_scraped: '12/20/2023',
    source: 'city scrape',
    name: 'Rental unit in Sheung Wan · ★4.22 · Studio · 1 bed · 1 bath',
    neighborhood_overview: '',
    host_id: 304876,
    host_url: 'https://www.airbnb.com/users/show/304876',
    host_name: 'Brendan',
    host_since: '11/30/2010',
    host_location: 'Hong Kong',
    host_about: 'I was born in California and raised in Hong Kong. Went to college in the states and returned to Hong Kong a few years ago.  I absolutely love travelling around the region but Hong Kong has always welcomed me home and I look forward to showing off my home town and sharing all the little insights and local specialities with all my guests!',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '99%',
    host_is_superhost: 'f',
    host_neighbourhood: 'Sheung Wan',
    host_listings_count: 10,
    host_total_listings_count: 58,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood_cleansed: 'Central & Western',
    latitude: 22.28463,
    longitude: 114.15054,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 2,
    bathrooms_text: '1 bath',
    beds: 1,
    price: '$482.00',
    minimum_nights: 28,
    maximum_nights: 1125,
    minimum_minimum_nights: 28,
    maximum_minimum_nights: 28,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 28,
    maximum_nights_avg_ntm: 1125,
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 0,
    calendar_last_scraped: '12/20/2023',
    number_of_reviews: 151,
    number_of_reviews_ltm: 0,
    number_of_reviews_l30d: 0,
    first_review: '2/26/2011',
    last_review: '3/11/2022',
    review_scores_rating: 4.22,
    review_scores_accuracy: 4.04,
    review_scores_cleanliness: 4.55,
    review_scores_checkin: 4.43,
    review_scores_communication: 4.51,
    review_scores_location: 4.73,
    review_scores_value: 4.13,
    instant_bookable: 'f',
    calculated_host_listings_count: 9,
    calculated_host_listings_count_entire_homes: 5,
    calculated_host_listings_count_private_rooms: 4,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 0.97
  },
  {
    _id: ObjectId('660deed0b6515eb205792dfe'),
    id: 132773,
    listing_url: 'https://www.airbnb.com/rooms/132773',
    scrape_id: 20231200000000,
    last_scraped: '12/21/2023',
    source: 'city scrape',
    name: 'Rental unit in Hong Kong Island · ★4.52 · 2 bedrooms · 3 beds · 1 bath',
    neighborhood_overview: `The Sheung Wan neighbourhood is ever changing and a fantastic mix of "old' and "new" Hong Kong.  This apartment is located in the heart of Hong Kong's commercial, cultural and shopping districts and within short walking distance to the subway and HK Macau Ferry Pier.  A few minutes walk away from the harbour front and the fantastic Sun Yat Sun Memorial Park and Public swimming pool over look the world famous Victoria Harbor.`,
    host_id: 304876,
    host_url: 'https://www.airbnb.com/users/show/304876',
    host_name: 'Brendan',
    host_since: '11/30/2010',
    host_location: 'Hong Kong',
    host_about: 'I was born in California and raised in Hong Kong. Went to college in the states and returned to Hong Kong a few years ago.  I absolutely love travelling around the region but Hong Kong has always welcomed me home and I look forward to showing off my home town and sharing all the little insights and local specialities with all my guests!',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '99%',
    host_is_superhost: 'f',
    host_neighbourhood: 'Sheung Wan',
    host_listings_count: 10,
    host_total_listings_count: 58,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood: 'Hong Kong Island, Hong Kong',
    neighbourhood_cleansed: 'Central & Western',
    latitude: 22.28921,
    longitude: 114.14325,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 6,
    bathrooms_text: '1 bath',
    beds: 3,
    price: '$1,475.00 ',
    minimum_nights: 5,
    maximum_nights: 365,
    minimum_minimum_nights: 5,
    maximum_minimum_nights: 5,
    minimum_maximum_nights: 365,
    maximum_maximum_nights: 365,
    minimum_nights_avg_ntm: 5,
    maximum_nights_avg_ntm: 365,
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 0,
    calendar_last_scraped: '12/21/2023',
    number_of_reviews: 247,
    number_of_reviews_ltm: 24,
    number_of_reviews_l30d: 3,
    first_review: '7/19/2011',
    last_review: '12/3/2023',
    review_scores_rating: 4.52,
    review_scores_accuracy: 4.49,
    review_scores_cleanliness: 4.7,
    review_scores_checkin: 4.6,
    review_scores_communication: 4.67,
    review_scores_location: 4.43,
    review_scores_value: 4.41,
    instant_bookable: 'f',
    calculated_host_listings_count: 9,
    calculated_host_listings_count_entire_homes: 5,
    calculated_host_listings_count_private_rooms: 4,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 1.63
  }
]
```
2. Show exactly 10 documents in any order, but "prettyprint" in easier to read format, using the pretty() function. Here is the code:
```
db.listings.find().limit(10).pretty()
```
Here is the result:
```
[
  {
    _id: ObjectId('660deed0b6515eb205792dfd'),
    id: 72571,
    listing_url: 'https://www.airbnb.com/rooms/72571',
    scrape_id: 20231200000000,
    last_scraped: '12/20/2023',
    source: 'city scrape',
    name: 'Rental unit in Sheung Wan · ★4.22 · Studio · 1 bed · 1 bath',
    neighborhood_overview: '',
    picture_url: 'https://a0.muscache.com/pictures/2849554/d226294d_original.jpg',
    host_id: 304876,
    host_url: 'https://www.airbnb.com/users/show/304876',
    host_name: 'Brendan',
    host_since: '11/30/2010',
    host_location: 'Hong Kong',
    host_about: 'I was born in California and raised in Hong Kong. Went to college in the states and returned to Hong Kong a few years ago.  I absolutely love travelling around the region but Hong Kong has always welcomed me home and I look forward to showing off my home town and sharing all the little insights and local specialities with all my guests!',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '99%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: 'Sheung Wan',
    host_listings_count: 10,
    host_total_listings_count: 58,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood: '',
    neighbourhood_cleansed: 'Central & Western',
    latitude: 22.28463,
    longitude: 114.15054,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 2,
    bathrooms_text: '1 bath',
    beds: 1,
    price: '$482.00',
    minimum_nights: 28,
    maximum_nights: 1125,
    minimum_minimum_nights: 28,
    maximum_minimum_nights: 28,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 28,
    maximum_nights_avg_ntm: 1125,
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 0,
    calendar_last_scraped: '12/20/2023',
    number_of_reviews: 151,
    number_of_reviews_ltm: 0,
    number_of_reviews_l30d: 0,
    first_review: '2/26/2011',
    last_review: '3/11/2022',
    review_scores_rating: 4.22,
    review_scores_accuracy: 4.04,
    review_scores_cleanliness: 4.55,
    review_scores_checkin: 4.43,
    review_scores_communication: 4.51,
    review_scores_location: 4.73,
    review_scores_value: 4.13,
    instant_bookable: 'f',
    calculated_host_listings_count: 9,
    calculated_host_listings_count_entire_homes: 5,
    calculated_host_listings_count_private_rooms: 4,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 0.97
  },
  {
    _id: ObjectId('660deed0b6515eb205792dfe'),
    id: 132773,
    listing_url: 'https://www.airbnb.com/rooms/132773',
    scrape_id: 20231200000000,
    last_scraped: '12/21/2023',
    source: 'city scrape',
    name: 'Rental unit in Hong Kong Island · ★4.52 · 2 bedrooms · 3 beds · 1 bath',
    neighborhood_overview: `The Sheung Wan neighbourhood is ever changing and a fantastic mix of "old' and "new" Hong Kong.  This apartment is located in the heart of Hong Kong's commercial, cultural and shopping districts and within short walking distance to the subway and HK Macau Ferry Pier.  A few minutes walk away from the harbour front and the fantastic Sun Yat Sun Memorial Park and Public swimming pool over look the world famous Victoria Harbor.`,
    picture_url: 'https://a0.muscache.com/pictures/36936441/e4c1f31d_original.jpg',
    host_id: 304876,
    host_url: 'https://www.airbnb.com/users/show/304876',
    host_name: 'Brendan',
    host_since: '11/30/2010',
    host_location: 'Hong Kong',
    host_about: 'I was born in California and raised in Hong Kong. Went to college in the states and returned to Hong Kong a few years ago.  I absolutely love travelling around the region but Hong Kong has always welcomed me home and I look forward to showing off my home town and sharing all the little insights and local specialities with all my guests!',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '99%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: 'Sheung Wan',
    host_listings_count: 10,
    host_total_listings_count: 58,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood: 'Hong Kong Island, Hong Kong',
    neighbourhood_cleansed: 'Central & Western',
    latitude: 22.28921,
    longitude: 114.14325,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 6,
    bathrooms_text: '1 bath',
    beds: 3,
    price: '$1,475.00 ',
    minimum_nights: 5,
    maximum_nights: 365,
    minimum_minimum_nights: 5,
    maximum_minimum_nights: 5,
    minimum_maximum_nights: 365,
    maximum_maximum_nights: 365,
    minimum_nights_avg_ntm: 5,
    maximum_nights_avg_ntm: 365,
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 0,
    calendar_last_scraped: '12/21/2023',
    number_of_reviews: 247,
    number_of_reviews_ltm: 24,
    number_of_reviews_l30d: 3,
    first_review: '7/19/2011',
    last_review: '12/3/2023',
    review_scores_rating: 4.52,
    review_scores_accuracy: 4.49,
    review_scores_cleanliness: 4.7,
    review_scores_checkin: 4.6,
    review_scores_communication: 4.67,
    review_scores_location: 4.43,
    review_scores_value: 4.41,
    instant_bookable: 'f',
    calculated_host_listings_count: 9,
    calculated_host_listings_count_entire_homes: 5,
    calculated_host_listings_count_private_rooms: 4,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 1.63
  },
  {
    _id: ObjectId('660deed0b6515eb205792dff'),
    id: 163664,
    listing_url: 'https://www.airbnb.com/rooms/163664',
    scrape_id: 20231200000000,
    last_scraped: '12/20/2023',
    source: 'city scrape',
    name: 'Rental unit in Sheung Wan · ★4.28 · 2 bedrooms · 3 beds · 1 bath',
    neighborhood_overview: 'Fantastic traditional Hong Kong neighborhood with lots of history at every street alley and corner.  Local restaurants are a treat to experience and public transport is all around to get you to all places of the city.',
    picture_url: 'https://a0.muscache.com/pictures/15184030/8d06b40b_original.jpg',
    host_id: 304876,
    host_url: 'https://www.airbnb.com/users/show/304876',
    host_name: 'Brendan',
    host_since: '11/30/2010',
    host_location: 'Hong Kong',
    host_about: 'I was born in California and raised in Hong Kong. Went to college in the states and returned to Hong Kong a few years ago.  I absolutely love travelling around the region but Hong Kong has always welcomed me home and I look forward to showing off my home town and sharing all the little insights and local specialities with all my guests!',
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '99%',
    host_is_superhost: 'f',
    host_thumbnail_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/users/304876/profile_pic/1359947330/original.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: 'Sheung Wan',
    host_listings_count: 10,
    host_total_listings_count: 58,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 't',
    host_identity_verified: 't',
    neighbourhood: 'Sheung Wan, Hong Kong',
    neighbourhood_cleansed: 'Central & Western',
    latitude: 22.28494,
    longitude: 114.14901,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 6,
    bathrooms_text: '1 bath',
    beds: 3,
    price: '$616.00',
    minimum_nights: 2,
    maximum_nights: 365,
    minimum_minimum_nights: 2,
    maximum_minimum_nights: 2,
    minimum_maximum_nights: 365,
    maximum_maximum_nights: 365,
    minimum_nights_avg_ntm: 2,
    maximum_nights_avg_ntm: 365,
    has_availability: 't',
    availability_30: 0,
    availability_60: 0,
    availability_90: 0,
    availability_365: 0,
    calendar_last_scraped: '12/20/2023',
    number_of_reviews: 225,
    number_of_reviews_ltm: 0,
    number_of_reviews_l30d: 0,
    first_review: '8/25/2011',
    last_review: '2/16/2021',
    review_scores_rating: 4.28,
    review_scores_accuracy: 4.24,
    review_scores_cleanliness: 4.41,
    review_scores_checkin: 4.44,
    review_scores_communication: 4.58,
    review_scores_location: 4.68,
    review_scores_value: 4.31,
    instant_bookable: 'f',
    calculated_host_listings_count: 9,
    calculated_host_listings_count_entire_homes: 5,
    calculated_host_listings_count_private_rooms: 4,
    calculated_host_listings_count_shared_rooms: 0,
    reviews_per_month: 1.5
  }
]
```
3. choose two hosts (by reffering to their host_id values) who are superhosts (available in the host_is_superhost field), and show all of the listings offered by both of the two hosts
only show the name, price, neighbourhood, host_name, and host_is_superhost for each result. Here is the code:
```
db.listings.find({ $or: [{ host_id: 1300549 }, { host_id: 634820 }] }, { name: 1, price: 1, neighbourhood: 1, host_name: 1, host_is_superhost: 1 })
```
Here is the result:
```
[
  {
    _id: ObjectId('660deed0b6515eb205792e01'),
    name: 'Rental unit in Sheung Wan · ★4.88 · 1 bedroom · 1 bed · 1 bath',
    host_name: 'Darren',
    host_is_superhost: 't',
    neighbourhood: 'Sheung Wan, Hong Kong',
    price: '$750.00'
  },
  {
    _id: ObjectId('660deed0b6515eb205792e10'),
    name: 'Hostel in Hong Kong · ★4.65 · 1 bedroom · 1 bed · 2.5 shared baths',
    host_name: 'Wontonmeen',
    host_is_superhost: 't',
    neighbourhood: 'Hong Kong',
    price: '$260.00'
  },
  {
    _id: ObjectId('660deed0b6515eb205792e11'),
    name: 'Hostel in Hong Kong · ★4.53 · 1 bedroom · 1 bed · 3 shared baths',
    host_name: 'Wontonmeen',
    host_is_superhost: 't',
    neighbourhood: '',
    price: '$280.00'
  },
]
```
By this code, we are supposed to focus on two superhosts. And then focus on their AirBnBs'neighbourhood and price.

4. find all the unique host_name values. Here is the code:
```
db.listings.distinct("host_name")
```
Here is the result:
```
['99 Bonham', 'A J', 'A&A']
```
By this code, we know the distinct hosts. We can not know the distict hosts by reading the raw data.

5. find all of the places that have more than 2 beds in a neighborhood of your choice (referred to as either the neighborhood or neighbourhood_group_cleansed fields in the data file), ordered by review_scores_rating descending.
only show the name, beds, review_scores_rating, and price.
if your data set only has blanks for all the neighborhood-related fields, or only one neighborhood value in all documents, you may pick another field to filter by - include an explanation and justification for this in your report.
if you run out of memory for this query, try filtering review_scores_rating that aren't empty ($ne); and lastly, if there's still an issue, you can set the beds to match exactly 2.
Here is the code:
```
db.listings.find(
  { beds: { $gt: 2 }, neighbourhood: "Sheung Wan, Hong Kong" },
  { name: 1, beds: 1, review_scores_rating: 1, price: 1 }
).sort({ review_scores_rating: -1 })
```
Here is the result:
```
[
  {
    _id: ObjectId('660deed0b6515eb205793a80'),
    name: 'Hotel in Sheung Wan · 2 bedrooms · 3 beds · 1 shared bath',
    beds: 3,
    price: '$17,066.00 ',
    review_scores_rating: ''
  },
  {
    _id: ObjectId('660deed0b6515eb205792e00'),
    name: 'Rental unit in Sheung Wan · ★4.35 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$1,210.00 ',
    review_scores_rating: 4.35
  },
  {
    _id: ObjectId('660deed0b6515eb205792dff'),
    name: 'Rental unit in Sheung Wan · ★4.28 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$616.00',
    review_scores_rating: 4.28
  }
]
```
By this code, we know a specific neighborhood with specific number of beds. In addition, they are ordered by review_scores_rating, so it is more convinent for us to find the best AirBnB which satisfies all requirements.

6. show the number of listings per host. Here is the code:
```
db.listings.aggregate([
  { $group: { _id: "$host_id", count: { $sum: 1 } } }
])
```
Here is the result:
```
[
  { _id: 107513223, count: 1 },
  { _id: 375221609, count: 2 },
  { _id: 199186201, count: 1 }
]
```
From this code, we can know each host has how many AirBnb.

7. find the average review_scores_rating per neighborhood, and only show those that are 4 or above, sorted in descending order of rating (see the docs)
if your data set only has blanks in the neighborhood-related fields, or only one neighborhood value in all documents, you may pick another field to break down the listings by - include an explanation and justification for this in your report.
Here is the code:
```
db.listings.aggregate([
  { $match: { review_scores_rating: { $gte: 4 } } },
  { $group: { _id: "$neighbourhood", avg_rating: { $avg: "$review_scores_rating" } } },
  { $sort: { avg_rating: -1 } }
])
```
Here is the result:
```
[
  { _id: 'Pat Heung, New Territories, Hong Kong', avg_rating: 5 },
  { _id: 'Hong Kong , Hong Kong', avg_rating: 5 },
  {
    _id: 'Tseung Kwan O, Le Prime, LOHAS Park, New Territories, Hong Kong',
    avg_rating: 5
  },
]
```
From this code, we can know which neighborhood has the highest average rating. Knowing this will help us choose the Airbnb.










