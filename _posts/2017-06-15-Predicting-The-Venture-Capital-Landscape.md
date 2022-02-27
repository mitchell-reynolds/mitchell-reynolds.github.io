---
title: Predicting the Venture Capital Landscape
published: true
---

Introduction
Where is the market headed? Will there be a slowdown or a rush for funding? What sectors are emerging or struggling?
Living in San Francisco startups fade and boom into conversations just as they do in the news and in the market. And as most residents of the Bay Area, I moved here to actualize the dreams of being part of the rising tide of change coming out of Silicon Valley. From my early fascination of startups, I felt motivated to better understand startups and started with funding.
Executive Summary
Through the use of machine learning, I am able to predict the trend of the overall venture capital market and what sectors are the most promising with relative confidence. Using Crunchbase data through 2013, I am able to predict the amount of funding for early 2014. Additionally, I predicted the most promising sector at that time being biotech and the worst sector being anything in social services. If given Crunchbase’s current proprietary data, I could easily predict funding for the rest of 2017.
Data Collection
Crunchbase hosts information about startups covering when those companies were funded, by whom, what sector and what backgrounds the founders have for that company. Crunchbase began in 2007 and operates by contributions made by users that are reviewed prior to being listed on the website. Crunchbase has made some of their data freely available in a MySQL format that provides all their information until the end of 2013. (1) In order to gain access, one must register as a researcher. However, one must register as a business and pay about six thousand dollars a year for access to their current data. Therefore, my scope of research will be on information freely available to glean insights of the past that could be easily replicated if given the most current data.

The Data Itself
Conveniently enough, I was able to extract and explore the data easily with a series of MySQL queries among the eleven files. After considerable exploration of all files, I used a few joins to work with one dataset: funding. Once in a DataFrame, I reorganized the structure to put it into a time series. Therefore, my variables are monthly time series data ranging from 2005 to 2013.

Crunchbase began in 2007 and has a significant amount of information for 2005 and onward.
My choice to limit the scope was based upon observing this histogram of unique number of investments per year. It’s important to note that users can contribute past information and that this histogram is purposefully narrowed as investment entries go back as early as the 1970’s.

Y Combinator, Techstars and SV Angel are the top three. Andreessen Horowitz rests in the middle with 76 commitments.

SV Angel, First Round Capital and Sequoia Capital. Although not shown, Sequoia Capital leads for the most number of commitments for Series B and in third for Series C.
Both of the above charts show all investors with at least 50 commitments. The top investors vary by what stage of funding. Y Combinator leads the pack for Seed stage funding, and SV Angel tops the list for Series A while being third for Seed stage.
Model Selection
I wanted two views for the state of startups. One view to see how the overall startup market would be performing and a second closer look at the Sector level.
The Overall Market (ARMA)
The market view analyzes total funding each month from the start of 2005 to the end of 2013. As this is a simple time series, I thought an autoregressive — moving-average (ARMA) model would be suitable. ARMA combines two models where each value is regressed on its past values and takes previous error terms as inputs and predicting the next value based on deviations from previous predictions. An error term is the difference between the predicted value and the actual value. The ARMA model is the standard tool when analyzing time series data.

Total Funding as reported from Crunchbase. The blue line is the monthly raw data in billions of inflation-adjusted USD and the red line shows the market trend (or the annual average).
The graph shows a dip in funding around 2009, which makes sense with The Great Recession. Then, funding increases steadily until the end of 2013.
Even though I have total funding per month, the first step to setting up an ARMA model is to induce stationarity. The theory behind transforming data into a stationary time series is to incorporate the inherently dependent structure of the data by differencing with relevant times. In other words, funding at one time is slightly dependent on last year and slightly dependent on last month. (2)

Each point is the difference while taking into account last month’s change (t-1) and last year’s change (t-12) and last year’s last month change (t-13) for each time (t).
The graph above is a stationary time series to be able to model and predict future funding. The mean of this series is very close to zero and has mostly a constant variance, which are the two requirements for stationarity. The two jumps shown will limit the confidence of my predictions yet prediction is still possible given slightly troublesome data. Before I discuss the results of the overall market, let’s focus on the Sector level.
Individual Sectors (LSTM)
Crunchbase has 42 pre-defined sector labels (e.g. hardware, travel, sports). I put each sector into its own time series from 2005 to 2013 for consistency. For this type of data, I thought a Long Short-Term Memory (LSTM) recurrent neural network (RNN) would work well. The LSTM was specifically designed to “remember” information over long periods of time. A simple RNN takes an input and through a set of weights (a layer) creates an output while also looping through those inputs then updating the weights. The LSTM operates the same way except the layer has four interrelated updates. The most important part of these four is the forget gate where either past information is kept or thrown away. The other three interact to create a filtered version of the input as an output. (3) This entire process is one epoch where the training data updates the weights within one iteration cycle.

Trends of the biotech, the software and the finance industry. The finance sector shows significant increase after the financial crisis signaling increased skepticism of current financial institutions.
Software had a slip in funding after 2009 while the finance sector increased significantly after 2010. Biotech during this entire period shows to have tripled. One great advantage for using an LSTM for all these different sectors is that differencing won’t be necessary as a neural network can learn the underlying dependent nature of the data.
Results
For the overall market view, my best ARMA model had an R-squared statistic of 0.452. The R-squared statistic ranges from 0 to 1 and represents how much variance of the data is captured by your model. The ARMA model does a descent job but doesn’t seem to fully account for large spikes in either direction. It does seem to capture that there will be jump of some sort but stays conservative in its prediction.
For the individual sectors view, my LSTM model had an R-squared value of 0.604 on the training data and 0.382 on the testing data. The training set consists of 2005 to 2012, and the testing set is all of 2013. The blue line in both graphs is the testing sets’ R-squared statistic and loss function value respectively. A loss function should be minimized as this is the measurement of deviations between the predicted and actual values. The R-squared (r2) graph shows how the LSTM model learns very quickly then levels off at around 400 epochs with minor improvement. The “loss” graph shows how the training and test sets converge.

For both graphs, the x-axis is the number of epochs.
The R-squared red crosshairs show where and at what value my model performed best. I could run this model for more epochs; however, the testing set begins to increase its variance signaling the model is beginning to overfit the training data thus will not generalize well to prediction.
Interpretation
The overall market was steadily increasing after 2012 and my model predicts this to continue into early 2014. Given the Crunchbase data, the startup sector had bounced back rather quickly from the financial crisis of 2008.
Hundreds of millions of dollars were predicted to flow into the biotech, cleantech, software, enterprise, E-commerce, mobile, and medical sectors. Biotech, cleantech and medical are particularly interesting because they’re shown to have the most growth during this time period. Software, enterprise, E-commerce, and mobile are the most funded sectors and most reliable for a flow of funding.
On the other hand, public relations, nonprofit, legal, local, and government sectors are the least promising sectors and all are predicted to have essentially no funding each month. The common thread strung around these sectors is that they are in a larger category of social services. However, does this mean that innovations aren’t possible here? I firmly believe not as these sectors need more innovation; yet, the profitability of these sectors are likely to be low.
Conclusion
The market maintained growth past 2012 with a steady inflow of funding. The biotech sector was emerging during this time as the most promising while social services lack representation for innovation.
Next, I intend to narrow my focus further to individual companies and their investors to better understand entrepreneurship and measure if certain investors have a significant affect on outcome. Most importantly, I plan to experience the life of entrepreneurship where knowing the movement of the market serves a significant value to one’s company.