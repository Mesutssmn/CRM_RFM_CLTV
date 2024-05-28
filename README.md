# CRM_RFM_CLTV

Business Problem
FLO wants to segment its customers to determine marketing strategies tailored to each segment. For this purpose, it is necessary to analyze customer behavior and create groups based on these behaviors.

Data Set Story
The dataset consists of information derived from the past shopping behaviors of customers who have shopped both online and offline between 2020 and 2021.

**master_id:** Unique customer ID

**order_channel:** The channel used for shopping (Android, iOS, Desktop, Mobile, Offline)

**last_order_channel:** The channel used for the last purchase

**first_order_date:** The date of the customer's first purchase

**last_order_date:** The date of the customer's last purchase

**last_order_date_online:** The date of the customer's last online purchase

**last_order_date_offline:** The date of the customer's last offline purchase

**order_num_total_ever_online:** Total number of purchases made online by the customer

**order_num_total_ever_offline:** Total number of purchases made offline by the customer

**customer_value_total_ever_offline:** Total amount spent by the customer on offline purchases

**customer_value_total_ever_online:** Total amount spent by the customer on online purchases

**interested_in_categories_12:** List of categories in which the customer has shopped in the last 12 months

**TASK 1:** Data Preparation
Read the flo_data_20K.csv dataset. Create a copy of the dataframe.

Define the outlier_thresholds and replace_with_thresholds functions needed to suppress outliers. Note: When calculating CLTV, frequency values should be integers. Therefore, round the lower and upper limits with round().

Suppress outliers for the variables "order_num_total_ever_online", "order_num_total_ever_offline", "customer_value_total_ever_offline", "customer_value_total_ever_online" if any.

Create new variables for each customer's total shopping number and expenditure, indicating that omnichannel customers shop from both online and offline platforms.

Examine variable types. Convert the types of variables that express dates to date type.

**TASK 2:** Creating the CLTV Data Structure
Take the date 2 days after the last shopping date in the dataset as the analysis date.

Create a new CLTV dataframe with customer_id, recency_cltv_weekly, T_weekly, frequency, and monetary_cltv_avg values. The monetary value will be expressed as the average value per purchase, while recency and tenure values will be expressed in weekly terms.

**TASK 3:** Establishing BG/NBD and Gamma-Gamma Models, Calculating CLTV
Fit the BG/NBD model.

Predict the expected purchases from customers within 3 months and add it to the cltv dataframe as exp_sales_3_month.

Predict the expected purchases from customers within 6 months and add it to the cltv dataframe as exp_sales_6_month.

Fit the Gamma-Gamma model. Predict the average value that customers will leave and add it to the cltv dataframe as exp_average_value.

Calculate the 6-month CLTV and add it to the dataframe as cltv.

Observe the top 20 customers with the highest CLTV values.

**TASK 4:** Creating Segments Based on CLTV
Divide all your customers into 4 groups (segments) according to the 6-month CLTV and add the group names to the dataset as cltv_segment.

Provide short action suggestions to management for 2 groups you will select from the 4 groups for 6 months.
