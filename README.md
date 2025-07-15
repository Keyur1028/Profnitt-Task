Step 0: Firstly lets understand the question.
        The question is asking us to predict the stock volatility of a given stock over the next n day period.The question doesnt directly ask to predict stock prices
        Now that we know what to do lets do it step wise.
Step 1: Library import
        We will be importing standard python libraries like yf,seaborn,pandas etc.
        Libraries like yahoo finance, seaborn and ta may not be readily available so pip install them
        Others can be simply imported
Step 2: Data install        
        Now that libraries are installed, we need data that the model will train on. This can simply be done using download function from yf. Using the stock ticker along with
        time period and OHLC interval.
        Note that the current model is using data since IPO (All time stock data) but it can simply be changed in the Data download cell manualy in the source code.
Step 3: Indicators
        Now that we have data we need to use indicators that help us to make useful predictions. We can implement a large number of variables and having more variables will lead 
        to a more accurate model. This is a simple model that uses MACD, RSI, EMA, SMA, Volume and Brollinger band.
Note: There is a failsafe if the amount of data is insufficient wrt the prediction we want to make. It basically checks how many days we want to predict is larger than the interval
selected

Step 4: Corellation matrix and Feature Dristibution
        The seaborn and mathplot libraries shine here.
        We can use these libraries to get heatmap corellatin matrix betwen the variables we took as input.
        These are given as output using plt.show() function.
Step 5: Model
        This is star of the entire code here. The model that is trained using stockdata using the random forest regression algorith. This is a ML algorithm that uses descision trees 
        along with several variables to reduce over or underfitting.
        It then undergoes a 80/20 test/train split(Basically analysing 80% data and predicting the rest)
        It also gives a mean squared error(Basically a measure of how accurate the model is for the variables
Step 6: Saving and using the model
        The model is useles sif cant use it to make predictions. Pickle library helps us to store and import the model when necessary.
Step 7: Data recalculation & Latest row retrival
        This is not a necessary step but is useful to get the most recent data in cases where the computation lakes longer or in short interval cases.
        We also retrieve the latest row of information which will be the base of predictions
Step 8: Output
        This is the point of the entire model. It spits out a n day volatility prediction .

Possible doubts:
1) Does this predict stock prices?
   No. It gives price volatility
2) Is this completely accurate?
   No. These numbers are merely prediction made using the most basic indicators. Several other factors may cause discrepancies. Dont trust these number blindly.
