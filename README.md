# Driver Coupons 
### Cource : Module 5 Berkeley
Link to my notebook: https://github.com/Minasardari/Berkeley_Module5_Coupons/blob/main/Driver_Coupon_MinaS.ipynb
### Problem Statement : 
Understanding consumer behavior is crucial for optimizing marketing strategies, especially when offering promotional discounts. This study aims to analyze the acceptance rates of **Bar** coupon acceptence rate as was asked in this module focusing on frequency of bar goers , passengars (e.g. if they have Kids) and occupation and for secondary investigation I investigated **Restaurant20To50** coupons, focusing on income groups, time of use, and age demographics. By leveraging bar charts and correlation matrices, we seek to:
1. Identify key factors influencing coupon acceptance rates.

2. Examine how frequency of going to bar/Resurant ,age, income and time of day interact to affect usage patterns.

3. Determine whether age groups exhibit significant differences in coupon redemption behavior.

4. Provide actionable insights for targeted promotions.



### Enhancing Analysis with Data Cleaning & Exploratory Data Analysis (EDA)
Since we need to make some decision we need to make sure we have clean data and perform an effective Exploratory Data Analysis (EDA)

## Step 1: Data Cleaning
✅ Removes duplicate records 

✅ Identifies & handles columns that are not really related or have dublicate values

   *direction_same* is same data as 'direction_opp' we can drop one
   
   *Car* doesn't seem like to have any relationship with Y and has so many missing data most so decided to drop column
    ![image](https://github.com/user-attachments/assets/1c32ff64-a8a2-4769-8f7b-7833b51361e6)

✅ Identifies & handles missing values 
   For categorical features I Impute missing values (replace with a suitable value)
   If dropping rows is not feasible due to significant data loss, imputation is an option.
   
   the nan column count is not significat we can remove rows but I notice the missing value are these columns only and decide to fill them with mode of eeach feature
     car 108,Bar 12577,CoffeeHouse 12467,CarryAway ,RestaurantLessThan20  12554,Restaurant20To50 12495

    For numerical features: we can use as follow 
      Mean/Median imputation (for continuous features)
      Mode imputation (for discrete features)
    There was not any NAN column numerical in this project to handle

    

✅ Ensures categorical consistency: using replace  for example on income so the data is more sorted in categoy and better on the charts
 for example here having $12... at the start of string put this oin the firstbar on bar chart data["income"] = data["income"].replace("Less than $12500", "$12499 or less")

## Step 2: EDA
✅ Checks distribution of numeric values 
   . for example temperature has valid values 
   . The Driver under 21 the bar going frequency should be never 

✅ Counts occurrences in categorical features 
  . using uniqe or Value_counts Helps identify distinct values Explore categorical columns to identify unique values and help find potential issues and inconsistent representations of the same value.(for example we don't have same data in category BAR frequency 1-3 and 1 to 3)
  . Helps identify distinct values 
  . Useful for checking unexpected categories
✅ Identify and handle numerical outliers
  Investigatiing that involves examining specific columns known to have issues based on data description
  e.g. check for invalid values or extreme outliers in 'temperature' and we observe the unit is Celsius (°C) t using box plot
  ![image](https://github.com/user-attachments/assets/8c06ce3b-d714-4483-8a9f-d92eb874bfc7)

#### Step 3: visualize the data to uncover patterns and insights
 ✅ Use a bar plot to visualize the coupon column.
![image](https://github.com/user-attachments/assets/95b798b3-59d8-4b14-9813-a65e2f0f6337)

✅ Use a histogram to visualize the temperature column.
![image](https://github.com/user-attachments/assets/3af6557e-3307-4e58-ac3a-4b0873081506)

✅ use a bra chart to show Acceptance Rate of Bar Coupons by Frequency of Bar Visits
![image](https://github.com/user-attachments/assets/0b3f40be-d7f5-44eb-96dd-5388bdb2dc20)

✅ Acceptance Rate of Restaurant20To50 Coupons by ag
![image](https://github.com/user-attachments/assets/73b0571c-0ae4-4b8c-9861-f08b5178bbfe)

✅ Acceptance Rate of Restaurant20To50 Coupons by time for each age group
![image](https://github.com/user-attachments/assets/b3650eea-612e-462f-a3f9-c2c5acf180db)

✅ Acceptance Rate of Restaurant20To50 Coupons by  Income and age_group shows affect both 
![image](https://github.com/user-attachments/assets/72a0681c-bbc5-4f1e-9a39-bec00df6ead5)





### Results and Findings

## Bar coupons 
Drivers who accept bar coupons more frequently tend to exhibit the following characteristics:

Frequent Bar Visits – Those who go to bars more than three times a month show higher acceptance rates.

Age Influence – Drivers aged 25 and older tend to accept bar coupons at a significantly higher rate (21- 25 even more).

Impact of Having Children – The presence of children as passengers reduces coupon acceptance, likely because parents may not have the flexibility to redeem the offer immediately.

Interacting Factors – Coupon acceptance is influenced by multiple variables, such as bar-going habits, absence of children, and specific occupations—creating distinct patterns in user behavior.

Hypothesis Regular bar-goers—especially those over 25 years old, without children in the car, and in certain professions—are more likely to accept bar coupons. Further occupation analysis could provide deeper insights into this trend.

## Restaurant (20-50) Specific coupons 

Income Level and Acceptance: Investigated the income levels and extract mode to see which age group whitin the income mode accept restaurant coupons. The analysis shows a notable income level where there's a significant trend in acceptance for certain age groups (21-50).

Age and Time Interactions: Acceptance rates for restaurant coupons also vary based on the time of day and the customer's age. Younger individuals between,21-50 might be more inclined to accept these coupons at specific times (10 AM, 10 pm) compared to older ones.

Combined Effect of Income and age group: The intersection of income level and age group impacts acceptance rates. Certain income groups showing in heap map which 71.34% for age group below 21 and income rate  37500 49999.


### Next to do 

## 1.Optimize Bar Coupon Promotions
📌 Target Frequent Bar-Goers group

Focus on individuals who visit bars 3+ times a month by giving some way to keep track of Bar checkins if we have app can do check in in app and send coupon to emmail or phone number 
Partner with bars offering exclusive deals for regular patrons and send offers to most frequent Bar goer

📌 Leverage Age-Based Offers

Create tiered discounts for ages 21-25, as they accept bar coupons most and target the area this group socilize or work or study 
Send coupos to work place schools
Promote offers during peak social hours (evenings & weekends)

📌 Consider Family Influence

Offer family-friendly alternatives for parents who are less likely to redeem bar coupons maybe coffee or resturant coupon offers to them on app
Market towards child-free social events

## 2.Enhance Expensive Restaurant Coupon Strategies
📌 Time-Based Optimization

Push restaurant coupons via sms or email around peak 10 AM & 10 PM—peak acceptance times for younger individuals  
Partner with resturants offering exclusive deals at other times to increase diners in other times low peak
Use limited-time promotions during high-acceptance periods

📌 Income-Level Adjustments

People earning $37,500-$49,999 (below 21 group) have 71.34% acceptance rates—focus on these segments ,Customize offers based on disposable income levels

📌 Age-Group Differentiation

Younger adults respond well to digital coupons—use SMS, app-based discounts Ensure QR codes, one-click redemption, or digital wallets for easy access

Older demographics prefer physical coupons or loyalty-based rewards


