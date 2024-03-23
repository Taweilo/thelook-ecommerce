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
The goal is to utilize SQL queries to delve into the dataset and extract valuable insights that can enhance business performance for Adidas. This includes areas such as sales optimization, marketing effectiveness, and supply chain management efficiency.

## 3. Analysis
### 1) Overall KPI 
- Compared with Competitors in 2024 Jan
     
| Brand         | Total Revenue ($) | Total Cost ($) | Gross Profit ($) | Market Share (%) |
|---------------|---------------|------------|--------------|------------------|
| Adidas        | 1623.87       | 682.8      | 941.07       | 29%              |
| New Balance   | 50.25         | 26.96      | 23.29        | 1%               |
| Nike          | 1820.58       | 879.08     | 941.5        | 32%              |
| Puma          | 782.01        | 346.22     | 435.79       | 14%              |
| Reebok        | 361           | 156.98     | 204.02       | 6%               |
| Under Armour  | 1057.31       | 475.51     | 581.8        | 19%              |

Total overall revenue: 5695.02

- Adidas regional performance in 2024 Jan
  
| Country        | Total Revenue ($) | Total Cost ($) | Gross Profit ($) |
|----------------|---------------|------------|--------------|
| Belgium        | 903           | 375.65     | 527.35       |
| China          | 240.88        | 102.91     | 137.97       |
| Brasil         | 154           | 63.11      | 90.89        |
| United States  | 136           | 60.11      | 75.89        |
| Japan          | 67.99         | 32.36      | 35.63        |
| United Kingdom | 55            | 21.99      | 33.01        |
| France         | 42            | 16.3       | 25.7         |
| Germany        | 25            | 10.38      | 14.62        |

### 2) Sales trends

<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/2.%20Sales%20Trend.jpg">

| Time   | Total Revenue ($) | Total Cost ($) | Gross Profit ($) |
|--------|---------------|------------|--------------|
| 2023-01| 653.74        | 281.38     | 372.36       |
| 2023-02| 453.73        | 206.91     | 246.82       |
| 2023-03| 390.11        | 163.15     | 226.96       |
| 2023-04| 440.15        | 181.56     | 258.59       |
| 2023-05| 867.98        | 421.19     | 446.79       |
| 2023-06| 598.77        | 263.04     | 335.73       |
| 2023-07| 817.9         | 360.38     | 457.52       |
| 2023-08| 691.95        | 293.02     | 398.93       |
| 2023-09| 348.8         | 170.47     | 178.33       |
| 2023-10| 1276.68       | 605.4      | 671.28       |
| 2023-11| 839.52        | 361.42     | 478.1        |
| 2023-12| 1952.84       | 865.8      | 1087.04      |
| 2024-01| 1623.87       | 682.8      | 941.07       |


### 3) Product performance
   
- top 10 adidas's popular product
  
| Product ID | Name                                                         | Purchase Frequency | Category    |
|------------|--------------------------------------------------------------|--------------------|-------------|
| 16106      | Adidas Golf Men's ClimaLite 3-Stripes Cuff Polo Sport Shirt. A76 | 3                  | Tops & Tees |
| 18264      | adidas Team Speed Crew Sock                                   | 2                  | Active      |
| 2594       | Adidas Womens Lightweight Trefoil Track Jacket                | 2                  | Active      |
| 2545       | adidas Women's Response Drei Streifen Short-Sleeve Tee        | 2                  | Active      |
| 18555      | Adidas Mens Sueded Hooded Fleece Pullover Hoodie Gray        | 1                  | Active      |
| 18541      | adidas Men's Athletic Stretch 2-Pack Trunk                    | 1                  | Active      |
| 24768      | adidas Men's Climalite II Low Cut Sock (2-Pack)               | 1                  | Socks       |
| 2785       | adidas Women's Superlite II No Show Sock (6-Pack)             | 1                  | Active      |
| 2914       | adidas Women's Response Tee                                   | 1                  | Active      |
| 18623      | adidas Men's Athletic Comfort Climalite 2-Pack Boxer Brief    | 1                  | Active      |

- top 10 adidas's cancelled product
  
| Product ID | Name                                                           | Cancelled Frequency | Category |
|------------|----------------------------------------------------------------|---------------------|----------|
| 18715      | adidas Men's Tech Fleece Pullover Hoodie                         | 1                   | Active   |
| 18054      | adidas Men's 3 Stripe Pant                                       | 1                   | Active   |
| 18550      | adidas Men's Response Drei Streifen Sleeveless Tee                | 1                   | Active   |
| 2542       | Adidas Womens CLIMALITE Lightweight Athletic Long Sleeve V-neck Tee Shirt | 1             | Active   |
| 18515      | adidas Men's Techfit Powerweb Short-Sleeve Tee                    | 1                   | Active   |
| 18267      | Adidas Condivo Men`s Training Pants                               | 1                   | Active   |
| 3059       | adidas Women's Response DS Short-Sleeve Tee W Short-Sleeve Top    | 1                   | Active   |

- top 10 adidas's returned product
  
| Product ID | Name                                                       | Returned Frequency | Category |
|------------|------------------------------------------------------------|--------------------|----------|
| 3042       | Adidas Ladies 3-stripe Long Sleeve Athletic V-neck Tee White | 1                  | Active   |
| 18670      | Adidas Mens Athletic LAX Shorts                              | 1                  | Active   |
| 2426       | adidas Women's Tiro 11 Training Pant                         | 1                  | Active   |
| 18204      | adidas Men's Sport Performance Climalite 2-Pack Trunk        | 1                  | Active   |


### 4) Customer profile
   
- Age Group profile
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/4.%20Age%20Group%20Profile.jpg">

- Country profile
  
| Country        | Customer Number |
|----------------|-----------------|
| China          | 11              |
| Brasil         | 5               |
| United States  | 5               |
| France         | 1               |
| Australia      | 1               |
| South Korea    | 1               |

- Gender profile
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/4.%20Gender%20Profile.jpg">

- Buying Behavior
  
| Metric          | Value |
|-----------------|-------|
| AOV  ($)           | 33.98 |
| APF  ($)           | 1.0   |
| Customer Value ($)  | 33.98 |


| Metric         | Average Value |
|----------------|---------------|
| Avg_recency (Day)   | 13.38         |
| Avg_frequency (Times)  | 1.0           |
| Avg_monetary ($)  | 36.91         |

### 5) Delivery efficiency
|      | Avg. Lead Time (Day) | Avg. Shipping Duration (Day)|
|------|----------------|-----------------------|
| 2024-01 | 3.56           | 3.08                  |
| 2023    | 3.05           | 2.48                  |
   
### 6)  New customer's preference
- Traffic source
<img width="60%" src="https://github.com/Taweilo/theLook_CRM/blob/main/Image/6.%20New%20Customer%20-%20Traffic%20Source.jpg">

- Buying Behavior
  
| brand        | brand_purchase_by_new_customer  | revenue ($) |
|--------------|--------------------------------|---------|
| Nike         | 13                             | 585.46  |
| adidas       | 12                             | 408.89  |
| PUMA         | 7                              | 210.97  |
| Under Armour | 5                              | 174.93  |
| Reebok       | 2                              | 127.00  |
| New Balance  | 1                              | 14.99   |
