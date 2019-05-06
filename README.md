# Closing_Loop

Many scholars believe that learning analytics will not demonstrate real utility until it can "Close the Loop", use data to automate decision making. A common example of this system are email generators that send emails to students in response to an activity (or lack of activity). Several universities have had some success with this strategy such as George Washington University. There are an infinite number of these lopp closing activities that could be implemented and there is a lot of work to be done understanding when they are most useful.

### Twitter Setup

Step 1. Create a Twitter account at Twitter.com and register as a developer at the following link: https://developer.twitter.com/

Step 2. Register a new app (we need to create an app to access the API as that is what the primary us of the API is) at https://apps.twitter.com/

Step 3. Within R, install the packages ROAuth and twitteR

Step 4. Copy the details from Twitter App page.

I can now download Tweets (but I can only search from the previous 6-7 days). Limit the number of tweets when searching for a popular term.

### Download Tweets
```{r}
library(dplyr)
TL1 <- searchTwitter("education data", n=300, since='2019-04-30', until='2019-05-01')
TL2 <- searchTwitter("education data", n=300, since='2019-05-02', until='2019-05-03')
TL1 <- do.call("rbind", lapply(TL1, as.data.frame))
TL2 <- do.call("rbind", lapply(TL2, as.data.frame))
TL<-as.data.frame(bind_rows(TL1, TL2))
```

Look at the data that Twitter has made available and do a quick visualization of Tweets over time.


![hist1](https://github.com/ab4499/Closing_Loop/blob/master/graphs/hist1.png "github")
![hist2](https://github.com/ab4499/Closing_Loop/blob/master/graphs/hist2.png "github")

![line1](https://github.com/ab4499/Closing_Loop/blob/master/graphs/line1.png "github")
![line2](https://github.com/ab4499/Closing_Loop/blob/master/graphs/line2.png "github")


