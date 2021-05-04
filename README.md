<h3 align="center">Financial Planning Using Monte Carlo Analysis</h3>
<p align="center">
  <a href="https://github.com/bgregory0913/">
    <img src="FinancialPlanning.PNG" alt="FinancialPlanning" align="center">
  </a>
</p>


# Project Overview:
* The intention of this project is to develop a prototype application to demo forecasting that helps investors enhance their financial wealth to create a reasonably good retirement plan based on cryptocurrencies, stocks, and bonds.
* This project focuses on using API's as part of the technical solution to create two financial analysis tools.
* The first tool is a personal finance planner that allows investors to visualize savings composed by investments in shares and cryptocurrencies to assess if they have enough money as an emergency fund.
* The second tool is a retirement planning solution that uses the Alpaca API to fetch historical closing prices for a portfolio composed of stocks and bonds, then run Monte Carlo simulations to project the portfolio performance at X amount of years. You can then use the Monte Carlo data to calculate expected returns from a specified initial investment amount.
* You can also adjust the portfolio to include more risk (higher stock to bond ratio) or to have a larger initial investment and rerun the  analysis to see what it would take to retire in 5 or 10 years vs. 30.


### Part 1 - Personal Financial Planner
In this section, we take into account the following assumptions:
* Assume the following number of shares in stocks and bonds: 50 SPY (stocks) and 200 AGG (bonds).

__Collect Crypto Prices Using the requests Library:__
* Fetch the current price in US dollars of bitcoin (BTC) and ethereum (ETH) using the Alternative Free Crypto API endpoint.
     * Parse the API JSON response to select only the crypto prices and store each price in a variable.
     * The identifier for each cryptocurrency in the API JSON response is different - the Bitcoin identifier is 1 and Ethereum is 1027.
* Plot a pie chart to visualize the composition of personal savings using the 'df_savings' DataFrame.
* Use conditional statements to validate if the current savings are enough for an emergency fund (an ideal emergency fund should be equal to three times monthly income).
     * If total savings are greater than the emergency fund, a message is displayed congratulating the person for having enough money in this fund.
     * If total savings are equal to the emergency fund, a message is displayed congratulating the person on reaching their financial goal.
     * If total savings are less than the emergency fund, a message is displayed stating how many dollars away the person is from reaching the goal.


### Part 2 - Retirement Planning
Use the Alpaca API to fetch historical closing prices for a retirement portfolio and the MCForecastTools toolkit to create Monte Carlo simulations, we can project the portfolio performance at X amount of years.

__Monte Carlo Simulation:__
* Using Alpaca, we fetch five years of historical closing prices for a traditional 40/60 portfolio using the SPY and AGG tickers to represent 60% stocks (SPY) and 40% bonds (AGG) composition of the portfolio.
* Then we execute a Monte Carlo Simulation of (500) runs and (30) years for the 40/60 portfolio.
* Again, we plot the results and the probability distribution/confidence intervals from the MC simulation.


## Resources
This project is written in Python using Jupyter Notebook and plotted with Pandas plots as well as additional libraries and modules listed below

* [Python](https://www.python.org/)
* [JupyterNotebook](https://jupyter.org/)
* [MapBox](https://www.mapbox.com/)
* [NumPy](https://numpy.org/)
* [HoloViews](http://holoviews.org/)
* [Panels](https://panel.holoviz.org/reference/panes/HoloViews.html)

### This tool uses the following two APIs:
* The Alpaca API to pull historical stocks and bonds information:
     * [AlpacaDOCS](https://alpaca.markets/docs/)
* The Alternative Free Crypto API to retrieve Bitcoin and Ethereum prices:
     * [Free Crypto API Documentation](https://alternative.me/crypto/api/)


### To run the notebook yourself:
* Download the files in the 'Code' folder and create a .env file with your Alpaca API key and Alpaca Secret Key in the same directory. If deploying to your own github, remember to add the .env file extension to your .gitignore configuration to avoid exposing your API keys in your repo.
* For faster execution during the Monte Carlo simulation, start by running 100 simulations for one year of returns. When you have the code figured out, run a full 500 simulations for 30 years.

## Contact:
Blake Gregory - [LinkedIn](www.linkedin.com/in/blake-greg) - blake.gregory@tilineum.com
