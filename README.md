# Cupon-Offline-Usage-Data-Analysis
## 1. Project Overview
With the widespread adoption and continuous improvement of mobile devices, the integration of mobile internet with various industries has entered a stage of rapid growth. Among these, O2O (Online to Offline) consumption has drawn particular attention. According to incomplete statistics, there are at least ten O2O startups valued at over one billion RMB, and even several giants worth tens of billions. The O2O sector connects hundreds of millions of consumers, with billions of user behavior and location data recorded every day across different apps. As such, it has become one of the best intersections between big data research and business operations.  

Using coupons to reactivate dormant users or attract new in-store customers is a key marketing strategy in O2O. However, randomly distributing coupons causes meaningless disturbance to most users. For merchants, uncontrolled coupon issuance can harm brand reputation and make marketing costs difficult to estimate. Personalized coupon targeting, therefore, plays a crucial role in improving coupon redemption rates — allowing users with specific preferences to enjoy real benefits while enabling merchants to conduct more effective marketing.

## 2. Analysis Objectives
1. Analyse the factors influencing store popularity and customer flow.  
2. Analyse consumer spending habits.  
3. Analyse the usage patterns of issued coupons.

## 3. Data Source
This dataset provides real online and offline consumer behavior data between January 1, 2016, and June 30, 2016.

## 4. Data Analysis
Only offline transaction data is used in this analysis.

**Table: Offline Transaction Data (ccf_offline_stage1_train.csv)**  

| Field | Description |
|:-|:-|
| User_id | User ID |
| Merchant_id | Merchant ID |
| Coupon_id | Coupon ID: null indicates a purchase without a coupon. In this case, Discount_rate and Date_received are meaningless. |
| Discount_rate | Discount rate: x∈ represents a discount ratio; x:y represents a full-X-reduce-Y type discount (in RMB). |
| Distance | Distance between the user’s frequently visited location and the merchant’s nearest store. Represented as x×500 meters, where x∈; null means no data; 0 means less than 500 meters; 10 means more than 5 km. |
| Date_received | Date when the coupon was received. |
| Date | Purchase date. If Date=null & Coupon_id≠null, it means the coupon was received but not used (negative sample). If Date≠null & Coupon_id=null, it means a normal purchase. If Date≠null & Coupon_id≠null, it means purchase using a coupon (positive sample). |

## 5. Conclusions
1. The most popular stores with high customer traffic are not significantly influenced by distance or discount rate, suggesting that product quality and customer experience are the main drivers of popularity.  
2. The proportion of used coupons to issued coupons is less than 10%, indicating that random coupon distribution is ineffective and leaves significant room for optimization.  
3. Personalized coupon targeting greatly improves redemption rates. Analysis identified a group of over 14,000 consumers labeled “shopping_mania” who show strong reliance on coupons, making them ideal targets for personalized campaigns.  
4. Further targeted and individualized distribution can be achieved by building machine learning models to capture consumption habits, enabling more accurate identification of suitable coupon recipients.

