# Stock Prediction Using Facebook Sentiment with Python
## Workshop Information
- Speaker: 游騰林
- Date: 2022-05-07 10:00 ~ 17:00
- Location: NCCU
- Link: 
  - [Github](https://github.com/TLYu0419/Stock-Prediction-Using-Facebook-Sentiment-with-Python)
  - [Facebook](https://www.facebook.com/nccumit/photos/a.690984424431809/1825960570934183/)
- Slide: To de upload. 
## Abstract: 
Stock market prediction has been a vital area of research for a long time. And there are many abroad study found that public mood sentiment on social media, such as Twitter, can predict the stock price effectively.[1, 2, 3, 4] 
But when it comes to Taiwan condiction, due to the difference in popular social media and the languages, both bring many problems and difficulties to building a stock price prediction model. 
To localize the technic with previous papers and give suggestions to investors, I develop a Python project about predicting the stock price through Facebook sentiment. 
This talk will share the five vital modules: data collection, data preprocessing, sentiment analysis, prediction model, and portfolio suggestion. After the analysis and model training process, I obtain 75% accuracy. It is very close to the reference literature. I hope this will help the investors get some valuable indicators and make better investment decisions.

許多研究都指出民眾在社群網站(Facebook, Twitter...)的發言內容，在經過情感分析抽取出的情感分數能夠有效預測未來的股價趨勢。在這次的工作坊中我將以 Facebook 的資料為例，帶著大家透過 Python 優雅的開發與收集 Facebook 在粉絲專頁/社團的資料，實作常見的情感分析方法與實務應用。最終再藉由抽取出的情感分數建置股價預測模型，幫助大家在進行投資時能增加一些具有價值和意義的參考指標

## Objective
1. To help people know what and how Python can help in investment strategy.  
2. Share some tips to collect the data from Facebook.
3. Demo 5 different methods to extract the sentiment from text data.
4. Explain how the results predicted by the model can be used in actual investment decisions. 

## Detail Descriptions
### Data collection 
In this project, we used data from two websites, Facebook and TWSE. The website with the more difficulty in collecting data is Facebook. If we want to collect data efficiently, two essential tips are how to use Facebook's graphql API and send requests directly to the Facebook server instead of Selenium. The second is that the Facebook server will limit the number of requests through cookie ID, so I will explain the website's structure and tell you how to obtain a new cookie from the server.

### Data preprocessing
In the stock market data, there are many missing values in the data due to weekends or national holidays. At the same time, the stock market data is very scarce, so we can't drop them easily. And how to fill these data is a crucial factor directly affecting the model's performance—referring to the Anshul Mittal et al.'s paper to fill in the missing value with the convex function. Here I will explain the principle of the convex function and demonstrate the Python script and its logic to fill these data.
Sentiment Analysis:
There are two stages in this section. The first is to extract the sentiment scores from Facebook data. The second is to analyze the correlation between sentiment scores and stock prices.

There are many ways to extract emotion from Facebook data, including through the posts' reactions themselves, which is through the users express the feeling types such as like, sad, haha, wow, angry, love and care. We can use these seven different types of sentiment to measure Facebook sentiment. Or we can use NLP sentiment analysis skills to extract sentiment from text messages. 
We can obtain sentiment scores in five ways: sentiment dictionary, sentiment analysis packages, translation, classification model, and web crawler. This section will compare the difference between them and show the attendees how to practice them through Python.

After we have the Facebook sentiment, we can further examine whether there are correlations between the sentiment score and the stock price. If so, we need to check how many days of sentiment score should be used in the stock price prediction model. However, if not, we can also analyze Facebook sentiment with different sentiment analysis methods to obtain other sentiment scores. Here we use the technique of the Granger causality statistic test, and I will explain how to perform Granger causality analysis and interpret the analysis results through Python. 

### Modeling
Once we have identified the explanatory and target variables, we then return to the task of the machine learning model. The explanatory variables we pass here include the sentiment scores of the past three days and the stock price of the current day and use these data to predict the stock price of the next day. After the test, we used the data from December 2021 to February 2022 as the training data and set the data from March 2022 as the test data. The experiment results showed that the accuracy of the model reached 75%. And we'll also share more model details and things to look out for here.

### Portfolio suggestion
Finally, I will establish some investment indicators based on the forecast results predicted by the model so that investors can understand the forecast results easily and make corresponding buy/sell decisions.

- Refernece:
  - Pagolu, V. S., Reddy, K. N., Panda, G., & Majhi, B. (2016, October). Sentiment analysis of Twitter data for predicting stock market movements. In 2016 international conference on signal processing, communication, power and embedded system (SCOPES) (pp. 1345-1350). IEEE.
  - Kharde, V., & Sonawane, P. (2016). Sentiment analysis of Twitter data: a survey of techniques. arXiv preprint arXiv:1601.06971.
  - Mittal, A., & Goel, A. (2012). Stock prediction using Twitter sentiment analysis. Standford University, CS229 (2011 http://cs229. stanford. edu/proj2011/GoelMittal-StockMarketPredictionUsingTwitterSentimentAnalysis. pdf), 15, 2352.
  - Bollen, J., & Mao, H. (2011). Twitter mood as a stock market predictor. Computer, 44(10), 91-94.
  - [徐琳宏, 林鸿飞, 潘宇, 任惠, & 陈建美. (2008). 情感词汇本体的构造. 情报学报, 27(2), 180-185.](http://ir.dlut.edu.cn/info/1013/1142.htm)
    - Download Link: [情感词汇本体-词典-信息檢索研究室](http://ir.dlut.edu.cn/info/1013/1142.htm)
  - [Shih-Ming Wang and Lun-Wei Ku. 2016. ANTUSD: A Large Chinese Sentiment Dictionary. In Proceedings of the Tenth International Conference on Language Resources and Evaluation (LREC'16), pages 2697–2702, Portorož, Slovenia. European Language Resources Association (ELRA).](https://aclanthology.org/L16-1428.pdf)