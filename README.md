# TwitterStockAnalysisV2

An updated version of TwitterStockAnalysis I worked on with Chuck K. during Zipcode Wilmington. Original code can be found here https://github.com/ZipcodeWizards/TwitterStockAnalysis

### Goals:
Stream tweets from twitter concerning Facebook, $FB prices from MarketWatch, and then plot tweet sentiment vs FB prices.

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
- images needed: mysql, and your app 
