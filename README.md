# DATA_SPARK
AIM OF THE PROJECT =
The aim of this project is to conduct a comprehensive Exploratory Data Analysis (EDA) of Global Electronics customer data, product data , sales data and store data to uncover valuable insights that will enhance customer satisfaction and drive business growth. And also the Project Motive include to do Marketing Strategies, Improve Sales, Developing Better Products,Plan Effective Promotions,Optimize Inventory Management. The ultimate goal is to provide actionable recommendations that will increase customer satisfaction and contribute to the overall growth of Global Electronics.
PROJECT STEPS = 
First we need to do Data Cleaning  Processand Preparation. For that we need to read the csv file. After this we need to check there is any Null Value is there for that me assigned one function (def null_value_imputer(df_customers)) null value imputer.In this function first the missing value is 80% and above it will totaly drop the column. Imputing missing values for Numeric Columns if the column containing the Numeric Values.If the skewness is low (between -0.4 and 0.4), missing values are filled with the Mean of the column.If the skewness is high (outside the range of -0.4 to 0.4), missing values are filled with the Median.Imputing missing values for categorical Columns if the column contains Categoric.For non-numeric (categorical) columns, missing values are filled with the most frequent value Mode.Need to call the function and then need to check any Null Values is there.Need to check any Duplicate value is there if any need to remove.Need to Check and Change the Column Name if Improper any.And then need to change the Data Types if anything is Improper.Once Cleaning the Data we need to store in csv file. 
Likewise same things need to Clean all the Data for Sales,Products,Store and Exchange_rates.
After that we need to Migrate these Cleaned Data to MYSQL.
For that we need to Create One Database for all the Data by using Different Tables.For that need to import pymysql.Need to execute the Cursor Connection. And then need to create Database name called 'Data'.
a=",".join(f"{i} {j}"
for i,j in zip(df_customers.columns,df_customers.dtypes)).replace("float64","float").replace("category","text").replace("int64","int").replace("object","text")  this code will do Combining Columns and Data Types and Replace the Data Types.After that we need to create Table name called Customer_data. sql = "insert into data.customers_data values"
for i in range(len(df_customers)):
    myconnection.cursor().execute(f"{sql} {tuple(df_customers.iloc[i])}")
    myconnection.commit() 
By using this code we can Push the Data into SQL Database. Likewise Same thing need to do for creating Individual Table for Sales_data,Products_data,Stores_data and Exchange_rate_data.

After Creating 10 Query at Sql we need to Export those things to Power Bi It will help to show in Visualization.

QUERY_1 = a)How does the number of customers vary by Country and Gender b) Which gender dominates the more overall?
SOLUTION = Male processed more order while comparing to Female. At the Same time, Here we need focus on Women like giving discounts especially for Womens and implimenting new products related to women usage
QUERY_2 = Finding the Average Age of the Customers by Country and Gender
SOLUTION = Mostly the Average age of the Male Customers is 55 to 57 likewise same to the Female Customers so we need to focus inbetween age of 45 to 60
QUERY_3 = Finding out the which Year and Month placed more Orders
SOLUTION = 2019 played major role for placing more orders especially at the seasonal time/festive time/end of the year. After Pandemic year the Sales got drop down at the low level.After Pandemic the Customers started to Ordering through Online. So we need to give some Coupons who are all making the purchase at Stores it will boost the customers to visit the Stores at Next Time.
QUERY_4 = Finding out that Which Category Soled Most
SOLUTION = Here Home Appliances played the Important Role in Sales rather than Game,Toys,Book Category because the average age of the Customers is 40-60. Rather than focusing on Game and Toys we need to focus on some more Category.
QUERY_5 = Finding out the Total.No.of.Sales by Category and Sub_Category
SOLUTION = In Each Category the Total no.of.Sales is differ by Sub_Category. We need to focus depend upon the each Products. For example if you take Computers,Camera,Cell Phones Sub_category means the Accessories Part sold out at very low level. For that we need to provide some Discounts,Offers etc.And also we need to add some more products at Home_Appliances Category.
QUERY_6 = Total Sales Values of Each Brand and Category
SOLUTION = Here we can know about which brand sold highest sales according to the price unit.And in Each Brand which Category Sold most of the Product.For Example Home Appliances are more sold at Contosco Brand so we need to do some BENCHMARK Analysis at some Brands.Why Customers are buying and what are the specialisations,features are there.
QUERY_7 = Finding Total no.of.Stores by each Country and State
SOLUTION = By using this we can found out how many stores are there in each State and Country.we can know about In which Country more Stores are present and in which country where we need to open the new stores.
QUERY_8 = Total Stores Opened by each Year
SOLUTION = This will helps us to know in which year the highest stores are opened.
QUERY_9 = Finding out Highest_Exchange_Rate by Currency
SOLUTION = Currency AUD has the highest exchange rate
QUERY_10 = Average Store size by County and State 
SOLUTION = By using the Chart we know about the Average Store Size of Each Country and State



