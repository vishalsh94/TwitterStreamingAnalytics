# TwitterStreamingAnalytics
This is an analytics project that streams popular tweet data from Twitter related to a trending word and then analyzes it using Hadoop.

Tasks to be done:-

a) Run a Map Reduce Program.

a1) The Mapper will fetch the name and the retweet count and favourites after delimiting with ~9

a2) Mapper will filter null user

a3) Mapper will also read hdfs file line by line . This file will be called say NeglectTweetersList.

a4) Mapper will filter the rows and not include those rows which have their names specified in that file i.e.  NeglectTweetersList

a5) Mapper will have key as User Name of the Tweeter. The corresponding value for the key would be in form of User Name@~RetweetCount@~Favourites Count

a6) Reducer will find the retweeters and favourites from the mappers output and find the net tweet count of that user using formulae :- 1 + retweeters count* 2 + faourites count *5 .

The result of all the reducer will come in form of 1 line per user like

Doug Cutting~9300 (where ~9 is delimiter and 300 is net tweet count)

This output file say X will be loaded into hive table TweetData

1) The table containg information of employee with the employer will be in mysql

2) This table will be loaded into hive table say MasterData using sqoop.

3) The final result will aggregate results for tweeters from same company into a hive table.

4) This table will be exported into hdfs file and then brought to local file system.
