# ETL Project

## GT Data Visualization BootCamp, Project 2 - ETL


With the arrival of the COVID-19 Pandemic and the subsequent market volatility, many have been looking at diversifying investments to secure a more stable portfolio. These investments can include stocks, bonds, real estate, cryptocurrency, and more. This project aims to look at daily market prices of the two most popular cryptocurrencies to better understand and study fluctuations and stability in the market.

The project showcases the ETL process, obtaining external data sources to extract, transform to useable tables, and load into a database for ease while querying. 



## Installation

This project was completed in an Anaconda environment which included the following Libraries: pandas, sqlalchemy, and psycopg2. 
In addition, pgAdmin was used to create and update the SQL database in PostgreSQL.

The initial external data files were sources from Kaggle.com: 

[Bitcoin Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/bitcoin-crypto)

[Ethereum Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/ethereum-crypto-price)



## Extract

The data sets were both downloaded as CSV files and placed in a folder in the repository. A Jupyter Notebook was then created to read and extract the CSV files into data frames.

[Bitcoin Historical Data (BTC Dataset)](Resources/BTC-USD.csv)

[Ethereum Historical Data (ETH Dataset)](Resources/ETH-USD.csv)



## Transform

The dataframes for both datasets currently contain columns for: Date, Open, High, Low, Close, Adj Close, and Volume. A new column was added and calculated the daily percent change in price for each cryptocurrency. There are the new base tables to use to build and produce the two finalized tables below.

### Table 1: BTC_ETH
The columns in each dataframe were renamed to specify BTC and ETH for Bitcoin and Ethereum respectively. This was done in preparation of merging the two dataframes together. The dataframes were merged on an inner join based on the Date. Therefore, only the dates which had data for both BTC and ETH were listed.

The dataframes were then filtered to remove any Null value dates and entries.

The finalized dataframe was labeled 'combined_df'. It is organized with one entry per date showing all of the data values for BTC and ETH for the day. 

### Table 2: Crypto

A column was added to both tables labeled 'Crypto' which labeled all of the Bitcoin entries at 'BTC' and all of the Ethereum entries as 'ETH'. The two tables were then appended to one another creating a new table that shows all of the daily prices for both cryptocurrencies.

The 'Date' column was converted to DateTime and the data was sorted in chronological order.

To clean the data, the dataframe was then filtered to remove any Null value dates and entries, and the index was reset to match the new chronological order.

The finalized dataframe was labeled 'raw_combined_df'. It is organized with 1-2 entries per date, but with each entry describing only one type of crytocurrency daily pricing data.



## Load

To load the data into a database, we chose PostgreSQL since the data sources had an expected schema and structure. Using a relational database allows us to store the tables into structured fields and defined columns. Since the data sets were relatively large, PostgreSQL was used and pgAdmin was used as the GUI to create and maintain the database.

SQLAlchemy was used to set up a declarative base and create classes for each table. A class was created for Table 1, called 'BTC_ETH' with all of the column names defined and id/Date set as the primary key. A second class was created for Table 2, called 'Crypto' with all of the column names defined and id set as the primary key.

A connection was established with the local database (PostgreSQL), a database named 'crypto_db' was created, and the tables were subsequently created in the database.

Data from 'combined_df' was loaded into the database as Table 'BTC_ETH'.
Data from 'raw_combined_df' was loaded into the database as Table 'Crypto'.


## Final Product

The finalized tables in the database were exported as CSV files and uploaded into the repository.

[BTC_ETH Table](Outputs/BTC_ETH.csv)

[Crypto Table](Outputs/Crypto.csv)



### Credits

Collaborators:

[Sanjay Dabra](https://github.com/skdabra30)

[Pranay Nuvvala](https://github.com/nuvvalaps)

Data Sources:

[Bitcoin Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/bitcoin-crypto)

[Ethereum Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/ethereum-crypto-price)
