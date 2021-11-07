Tools: NLTK, mysql, twitter API, pyspark, plotly, dash, docker, K8s

#### Tasks
1) Pipeline 1: twitter@fb > allTweets table > fetch from db and clean with pyspark > store cleaned data into cleanedTweets table > perform nltk analysis
2) Pipeline 2: marketwatch@fb > allPrices table > fetch from db and clean with pyspark > store cleaned data into cleanedPrices table
3) Plot daytime traidng hours of tweets vs $fb prices in plotly and then output it to a plotly dash front end where users can pick weekdays to see comparisons
4) package the app into a docker image and then use k8s to orchestrate a node with our app pod and a mysql database pod 

Notes: try not to use pandas, try to do data wrangling in spark