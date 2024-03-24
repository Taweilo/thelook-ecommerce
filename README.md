# theLook ecommerce Project

```
├── Image                       
│
├── Adidas_SQL code.ipynb                             <- SQL code
├── README.md                                         <- read me

```
## 1. Introduction
TheLook is a fictitious eCommerce clothing site developed by the Looker team. The dataset contains information about customers, products, orders, logistics, and web events. 

- Data source: https://console.cloud.google.com/marketplace/product/bigquery-public-data/thelook-ecommerce?hl=en&project=causal-flame-283208
- ER Diagram
<p align="center" width="100%">
    <img width="80%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/theLook_ER%20Diagram.jpg">
</p>

- Entity & Columns
  
| Table Name           | Columns                                                                                                                                                                        |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| users                | id, first_name, last_name, email, age, gender, state, street_address, postal_code, city, country, latitude, longitude, traffic_source, created_at                            |
| order_items          | id, order_id, user_id, product_id, inventory_item_id, status, created_at, shipped_at, delivered_at, returned_at, sale_price                                                    |
| distribution_centers | id, name, latitude, longitude                                                                                                                                                   |
| inventory_items      | id, product_id, created_at, sold_at, cost, product_category, product_name, product_brand, product_retail_price, product_department, product_sku, product_distribution_center_id |
| products             | id, cost, category, name, brand, retail_price, department, sku, distribution_center_id                                                                                          |
| orders               | order_id, user_id, status, gender, created_at, returned_at, shipped_at, delivered_at, num_of_item                                                                               |
| events               | id, user_id, sequence_number, session_id, created_at, ip_address, city, state, postal_code, browser, traffic_source, uri, event_type                                         |


## 2. Objective
The goal is to utilize SQL queries to delve into the dataset and extract valuable insights that can enhance business performance for theLook. This includes areas such as sales optimization, marketing effectiveness, and supply chain management efficiency.

## 3. Analysis
### 1) Overall KPI 
- Performance in 2024 Jan
  
| Total revenue ($) | Total_cost ($) | Gross Profit ($) |
|--------------|------------|--------------|
|   429657.13  |  206967.73 |   222689.4   |     


- Regional performance in 2024 Jan
  
| Country         | Total Revenue ($) | Total Cost ($) | Gross Profit ($) |
|-----------------|---------------|------------|--------------|
| China           | 138467.32     | 66301.64   | 72165.68     |
| United States   | 100700.23     | 48801.18   | 51899.05     |
| Brasil          | 68657.79      | 33080.71   | 35577.08     |
| South Korea     | 24216.06      | 11705.37   | 12510.69     |
| France          | 19089.77      | 9207.04    | 9882.73      |
| Germany         | 18142.38      | 8816.84    | 9325.54      |
| United Kingdom  | 18110.54      | 8781.01    | 9329.53      |
| Spain           | 14955.57      | 7135.92    | 7819.65      |
| Japan           | 10533.59      | 5087.42    | 5446.17      |
| Australia       | 9433.03       | 4496.55    | 4936.48      |
| Belgium         | 6197.96       | 2996.5     | 3201.46      |
| Poland          | 1002.05       | 492.47     | 509.58       |
| Colombia        | 150.84        | 65.08      | 85.76        |


### 2) Sales trends

<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/2.%20Sales%20Trend.jpg">

| Year | Month | Total Revenue ($) | Total Cost ($) | Gross Profit ($) |
|------|-------|---------------|------------|--------------|
| 2024 | 1     | 429657.13     | 206967.73  | 222689.4     |
| 2023 | 12    | 366083.04     | 175276.49  | 190806.55    |
| 2023 | 11    | 341790.55     | 163669.56  | 178120.99    |
| 2023 | 10    | 312906.78     | 150547.74  | 162359.05    |
| 2023 | 9     | 291911.42     | 140918.17  | 150993.25    |
| 2023 | 8     | 276600.05     | 133256.34  | 143343.71    |
| 2023 | 7     | 273314.5      | 130706.16  | 142608.34    |
| 2023 | 6     | 236056.66     | 112967.63  | 123089.03    |
| 2023 | 5     | 235039.45     | 113266.13  | 121773.32    |
| 2023 | 4     | 222483.69     | 107225.3   | 115258.39    |
| 2023 | 3     | 198496.66     | 94973.58   | 103523.08    |
| 2023 | 2     | 178984.28     | 85470.73   | 93513.56     |
| 2023 | 1     | 182464.59     | 87242.47   | 95222.12     |



### 3) Popular items
   
- top 10 popular category
  
| Category                       | Total Revenue ($) |
|--------------------------------|---------------|
| Outerwear & Coats              | 55557.22      |
| Jeans                          | 52617.5       |
| Sweaters                       | 31206.6       |
| Suits & Sport Coats            | 26493.46      |
| Swim                           | 25270.88      |
| Fashion Hoodies & Sweatshirts  | 24710.82      |
| Sleep & Lounge                 | 23366.28      |
| Shorts                         | 20524.36      |
| Tops & Tees                    | 18505.96      |
| Intimates                      | 17674.01      |
  


- top 10 popular brand
  
| Brand             | Total Revenue ($) |
|-------------------|---------------|
| Diesel            | 9709.7        |
| Calvin Klein      | 8587.29       |
| True Religion     | 7937.47       |
| Carhartt          | 7439.68       |
| 7 For All Mankind | 6021.58       |
| Joe's Jeans       | 4834.69       |
| Columbia          | 4274.04       |
| Tommy Hilfiger    | 4005.61       |
| Volcom            | 3838.44       |
| Allegra K         | 3805.76       |


- top 10 popular product
| Name                                                  | Total Revenue | Total Cost | Gross Profit | Unit Sold |
|-------------------------------------------------------|---------------|------------|--------------|-----------|
| Diesel Men's Lisardo Jacket                           | 1516          | 670.07     | 845.93       | 2         |
| Canada Goose Men's Lodge Jacket                       | 1200          | 532.8      | 667.2        | 3         |
| Nicole Miller Women's Halter Jumpsuit                 | 1100          | 612.7      | 487.3        | 2         |
| Alpha Industries Rip Stop Short                       | 999           | 482.52     | 516.48       | 1         |
| Nobis Yatesy Parka                                    | 950           | 381.9      | 568.1        | 1         |
| The North Face Apex Bionic Soft Shell Jacket - Men's  | 903           | 391.9      | 511.1        | 1         |
| Jordan Low Quarter Sock Style # 427411                | 903           | 537.29     | 365.71       | 1         |
| The North Face Women's S-XL Oso Jacket                | 903           | 378.36     | 524.64       | 1         |
| Mens Nike AirJordan Varsity Hoodie Jacket Grey / Black 451582-066 | 903   | 409.06     | 493.94       | 1         |
| AIR JORDAN DOMINATE SHORTS MENS 465071-100            | 903           | 454.21     | 448.79       | 1         |
  



### 4) Customer profile
   
- Age Group profile
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/4.%20Age%20Group%20Profile.jpg">

- Country profile
  


- Gender profile
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/4.%20Gender%20Profile.jpg">

- Buying Behavior
  
 | AOV   | APF  | Customer Value |
|-------|------|----------------|
| 83.75 | 1.05 | 87.78          |
 
| Avg_recency | Avg_frequency | Avg_monetary |
|-------------|---------------|--------------|
| 13.54       | 1.42          | 84.83        |




### 5) Delivery efficiency

|              | Avg Lead Time | Avg Shipping Duration |
|--------------|---------------|-----------------------|
| Overall      | 3.09          | 2.51                  |
| Domestic     | 3.00          | 2.48                  |
| Oversea      | 3.12          | 2.53                  |


### 6)  New customer's preference
- Traffic source
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/6.%20New%20Customer%20-%20Traffic%20Source.jpg">

  

