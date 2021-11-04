# TwitterStockAnalysisV2

An updated version of TwitterStockAnalysis I worked on with Chuck K. during Zipcode Wilmington. Original code can be found here https://github.com/ZipcodeWizards/TwitterStockAnalysis

### Goals:
Stream tweets from twitter concerning Facebook, $FB prices from MarketWatch, and then plot tweet sentiment vs FB prices.

### Cron Job:
DAG: 
- stream past 18000 tweets and past prices at 5:01 pm, eastern, M-F into a 
- fetch tweets and prices, clean, store in mysql database 

### Tech Stack/Packages:
- NLTK, mysql, twitter API, pyspark, plotly, dash, docker, K8s

### Tweet Steps:
- Stream tweets from twitter with twitter API and then store in a mysql database.
- fetch unclean tweets and drop duplicates
- Clean tweets with Databricks (UTC to EST, remove stop works with NLTK, dropping duplicates, keep only english tweets, group tweets by every 10 minutes and avg sentiment scores)

### $FB Steps:
- Fetch twitter prices 
- Clean prices by grouping prices every 10 minutes, and only looking at daytime trading hours

### Data Visualizations:
- perform data analysis with plotly and then dash to create a front end where uses can select a date and then see a plot of sentiment vs stock price 
- output app to heroku (?)

### Docker-Compose and K8s
- let docker-compose create the images and connections between images and then have K8s host the container. 
- images needed: mysql, my app, airflow

### Future Goals (TwitterGameAnalysisV1)
- (simple): take someone else's win probability graph of a football game and plot vs twitter sentiment during a live game. Tweets will be fetched with tweepy api *after* the game and then tweets will be plotted with win probability graph generated *after* the game.
- (complex): 1. create your own win probability statistical model and apply it to a historic NFL game to plot win probability. 2. Model will then be applied to a live game and compared to tweets from twitter API with relevant tweets timed before the play.
