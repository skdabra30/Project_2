# ETL Project

## GT Data Visualization BootCamp, Project 2 - ETL


With the arrival of the COVID-19 Pandemic and the subsequent market volatility, many have been looking at diversifying investments to secure a more stable portfolio. These investments can include stocks, bonds, real estate, cryptocurrency, and more. This project aims to look at daily market prices of the two most popular cryptocurrencies to better understand and study fluctuations and stability in the market.

The project showcases the ETL process, obtaining external data sources to extract, transform to useable tables, and load into a database for ease while querying. 


## Installation

This project was completed in an Anaconda environment which included the following Libraries: pandas, sqlalchemy, and psycopg2. 
In addition, PGAdmin was used to create and update the SQL database.

The initial external data files were sources from Kaggle.com: 
[Bitcoin Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/bitcoin-crypto)
[Ethereum Kaggle Data](https://www.kaggle.com/datasets/ranugadisansagamage/ethereum-crypto-price)


## Extract

The data sets were both downloaded as CSV files and placed in a folder in the repository. A Jupyter Notebook was then created to read and extract the CSV files into data frames.
[Bitcoin Historical Data (BTC Dataset)](Resources/BTC-USD.csv)
[Ethereum Historical Data (ETH Dataset)](Resources/ETH-USD.csv)


## Transform

The dataframes for both datasets currently contain columns for: Date, Open, High, Low, Close, Adj Close, and Volume. A new column was added and calculated the daily percent change in price for each cryptocurrency.



Provide instructions and examples for use. Include screenshots as needed.

To add a screenshot, create an `assets/images` folder in your repository and upload your screenshot to it. Then, using the relative filepath, add it to your README using the following syntax:

    ```md
    ![alt text](assets/images/screenshot.png)
    ```

## Credits

List your collaborators, if any, with links to their GitHub profiles.

If you used any third-party assets that require attribution, list the creators with links to their primary web presence in this section.

If you followed tutorials, include links to those here as well.


---



## Tests

Go the extra mile and write tests for your application. Then provide examples on how to run them here.