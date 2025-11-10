Project Report: Exploratory Analysis of Airbnb in 10 European Cities

To: European Commission for Sustainable Cities



From: group 5



Date: 10/11/2025



1\. Dataset OverviewItemDescriptionDataset nameEuropean Cities Airbnb DataNumber of rows51707Number of columns21 (After cleaning and feature engineering)Format file (.csv, .txt, etc).xlsx (Original)Authors of the datasetThis dataset was compiled for the research paper "The effect of Airbnb on housing prices in 10 European cities"Source (name)Mendeley DataSource (link)https://data.mendeley.com/datasets/btj7jgrj5y/1
2. Dataset Structure
Feature/variable,Data type,Description,Number of Unique values,Example values

Price,float64,The price per night in Euros,1290,"141.20, 210.00"

room\_type,object,The type of listing,3,"Entire home/apt, Private room"

person\_capacity,int64,The maximum number of guests,7,"2, 4"

host\_is\_superhost,bool,"Whether the host is a ""Superhost""",2,"True, False"

cleanliness\_rating,int64,Guest rating for cleanliness,10,"9, 10"

guest\_satisfaction\_overall,int64,Overall guest satisfaction score,65,"97, 100"

bedrooms,int64,The number of bedrooms,11,"1, 2"

dist,float64,Distance to the city center (km),3631,"3.30, 1.59"

metro\_dist,float64,Distance to the nearest metro (km),1003,"0.23, 1.01"

city,object,The city where the listing is,10,"berlin, paris"

country,object,The country where the listing is,10,"Germany, France"

day\_type,object,Whether the listing is for a weekday or weekend,2,"Weekday, Weekend"

host\_listings\_category,object,Number of listings the host has,3,"One listing, 5+ listings"

3\. Data cleaning
Issue,Names of Columns affected,Description of the Issue,Action Taken

Data Merging,city,Each city was in a separate sheet.,All 10 sheets were loaded and concatenated. A city column was added based on the sheet name.

Column Naming,realSum,Column for price was named realSum.,Renamed realSum to Price for clarity.

Missing Data,day\_type,The day column was missing from the import.,"Re-engineered day\_type and city from the raw city column (e.g., 'amsterdam\_weekdays')."

Categorical Encoding,"room\_shared, room\_private",Room type was stored in two separate binary columns.,"Combined into one room\_type column ('Entire home/apt', 'Private room', 'Shared room'). Dropped old columns."

Categorical Encoding,"biz, multi",Host listing count was stored in binary columns.,"Combined into one host\_listings\_category column ('One listing', '2-4 listings', '5+ listings')."

Feature Creation,country,Country data was missing.,Created country column by mapping from the clean city column.

4\. Descriptive statistics
,Price,person\_capacity,guest\_satisfaction\_overall,dist,metro\_dist

Count,51707,51707,51707,51707,51707

Mean,278.8,3.16,94.3,3.20,0.69

Std,344.2,1.30,8.2,2.70,0.81

Min,39.0,2.00,20.0,0.01,0.00

25%,129.0,2.00,92.0,1.30,0.28

50%,199.0,3.00,96.0,2.50,0.50

75%,321.0,4.00,100.0,4.20,0.80

Max,18525.0,16.00,100.0,25.00,14.28
Category columns
,room\_type,host\_is\_superhost,city,day\_type,host\_listings\_category

Count,51707,51707,51707,51707,51707

Unique,3,2,10,2,3

Top,Entire home/apt,False,Rome,Weekday,One listing

Freq (Top),37050,38555,5865,25867,25227
5. Analysis - Research question

(This is a sample for you to complete. You would write your text, then include the figures and captions you created in your notebook.)



Our analysis explores the Airbnb market across 10 European cities, focusing on patterns that might suggest housing pressure.



Finding 1: Listing Distribution and Room Type

The volume of listings varies significantly by city. Rome, Paris, and London dominate the dataset, each having over 5,000 listings. Across all cities, "Entire home/apt" is the most common listing type, making up 71.7% of all listings (as seen in the descriptive stats).



This high prevalence of entire home rentals, particularly in high-demand cities, is a key indicator for policymakers. It suggests a significant portion of the housing market is dedicated to short-term tourism rather than long-term residents.



(Insert Plot 4: Price by City and Room Type here)



Figure 1: Comparison of Log-Transformed Price by City and Room Type. This chart shows that "Entire home/apt" listings are consistently the most expensive option in every city. Prices are visibly higher in cities like London and Paris.



Finding 2: The "Superhost" Effect

We analyzed the "Superhost" designation as a proxy for professional or high-quality hosts. We found that Superhosts are not randomly distributed; some cities, like Vienna and Berlin, have a much higher proportion of them.



Our analysis shows that Superhosts are correlated with higher quality metrics. They have significantly higher median cleanliness ratings and guest satisfaction scores than normal hosts. Interestingly, they are not significantly more expensive, and their listings tend to be slightly closer to the city center. This suggests Superhosts compete on quality and location rather than just price.



(Insert Plot 9: Superhost Analysis (Price, Distance, Cleanliness) here)



Figure 2: Comparison of Superhosts vs. Normal Hosts. Superhosts consistently achieve higher cleanliness ratings (right). They are also located slightly closer to the city center (middle) and are not significantly more expensive (left).
Finding 3: Price, Capacity, and Housing Pressure

Finally, our analysis shows a clear and predictable relationship between listing price and guest capacity. As seen in our initial plots, the most common listings are for 2 or 4 people, which directly corresponds to the 1- and 2-bedroom apartments that form the core of the residential housing market.



As Figure 3 demonstrates, there is a strong positive correlation between capacity and price. Listings for 4 people are significantly more expensive than listings for 2 people, and so on.



(Insert Plot 11: Price vs. Person Capacity here)



Figure 3: Log-Transformed Price by Person Capacity. This chart shows a clear stepwise increase in price as the guest capacity of a listing grows.



This finding is central to the discussion of housing pressure. The data shows a robust and profitable market for 2-to-4-person "Entire home/apt" listings (which we identified as the most common type in Finding 1).



This financial incentive encourages property owners to convert standard 1- and 2-bedroom apartments—the most critical housing stock for local individuals, couples, and small families—from the long-term residential market to the short-term rental market. This reduction in available long-term housing is a well-documented driver of rent increases and residential displacement, both key indicators of gentrification.

