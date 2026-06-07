# YahooFinanceAnalysis

## Basic Info:
    POC: Mike Pogash
    Origin Date: May 09, 2026
    Revision History: 
    --------------------------------------------------------------------------------------------
    ID  |       Date      |    Description
    --------------------------------------------------------------------------------------------
    0   |   09-May-2026   |  initial baseline of code repo

## Usage
### Runnings
    - scritps.visualize_ticker_data.py ready to be deployed

## Project Description:

### Purpose: 
    PURPOSE 1: Brokerage Analysis
    - Loads brokerage data
    - Visualize it

    PURPOSE 2: Stock Analysis
    - Fetch stock trading and fundamental data from yFinance
    - Create figures
        - close price time series w/ volumne
        - ability to add other data, such as revenue, cash, shares outstanding, etc
    - Train an NN that uses various features to estimate stock price
        - Break down analysis by sectors
        - Expect large deviations from estimate stock price
        - Use as "guide" to identifying if a stock is trading as an outlier in its sector based
          on fundmental and trading data
        - Ex.
            - Use features:  P/S, P/E, EBITDA, Cash, Debt, and trends (P/S yoy growth, P/S 2 yr growth, P/S n yr growth)
            - Train NN with market cap or share price as dependent variabel, use all tickers in a sector to train model
            - With trained model, feedforward the features for a stock of interest to compute its estimate market cap or share price
            - Compute the difference between currrent and estiamte price, plot distribution of "premiums & discounts"
            ----> qualitatively, see if we can justify outliers, etc, company XYZ is trading with a premium in the top 3%
                  b/c new product launch has not yet hit revenue or compnay MNP is trading with a discount in the bottom 
                  6% b/c its product faces heavy competition from a new set of competitors and the future revenue growth is
                  expected to drop, but it had not yet occured
    - Other analysis products that would be interesting as well, besides a NN trained purely a mix of fundamental and trading, such as: 
        - How regularly does a company beat earnings expectations and by how much? Rrevenue expectations not
          availbile through yFinance
        - What is the historical P/S, P/E, (Cash-Debt)/MarketCap for a ticker? Where does it sit now  
          

### Current Capabilities
    - Figures of Price over time, with mov avg overlays and subplot of P/S 
    - Ability to Load in and visualize brokerage data

### Goal Capabilites:       
    - see purpose section 

### Limitations:

### Required Libraries & APIs:
    - numpy, matplotlib, tables, pandas, yfinance, reportlab

## Developer Notes

### Things To Do: 
    a lot
    
### Common Issues:
    - VSCode defaulting to enable copilot suggestions
         see ./debug/settings_json_configuration.txt

    - VS Code was used to access Ubtuntu WSL terminal to run this script. The command pallete, Python: Select 
      Interpreter, was used to select the appropriate Python environment with the necessary libraries installed.

    - GitHub did not want to talk to the Ubuntu terminal. Needed to call the line below from the Ubuntu terminal: 
      git config --global --add safe.directory '%(prefix)///wsl.localhost/Ubuntu/home/mike/GitHub/AIML_Demonstration'
