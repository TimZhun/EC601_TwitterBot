
# EC601_TwitterBot
Using Twitter, googleNLP and Bototmeter API to check someones account by sending twitter name and number of tweets to check:
**Example1:**
Checking last tweets
![enter image description here](https://i.imgur.com/nETbmjw.png)
**Example2:**
Checking BU account 
![enter image description here](https://i.imgur.com/R4MSJkK.png)

Using twitter api for Project 2
**Search tweets by Hashtags**
hashtag = '#Boston_University'
max_hash = 100
tweets = api.search_tweets(q = hashtag, count = max_hash, tweet_mode = 'extended')
for tweet in tweets:
    print(tweet.full_text)

![enter image description here](https://i.imgur.com/TjKGyOY.png)

###Getting some tweets of a user
user = 'osama_amaso'
max_limit = 10
tweets = api.user_timeline(screen_name = user, count = max_limit, tweet_mode = 'extended')
for  tweet  in  tweets:
print(tweet.full_text)
![enter image description here](https://i.imgur.com/g71GTfh.png)

###Writes last 20 twits in file tweets.csv
for  tweet  in  public_tweets:
print(tweet.text)
print(public_tweets[0].user.screen_name)
columns = ['Time', 'User', 'Tweet']
data = []
for  tweet  in  public_tweets:
data.append([tweet.created_at, tweet.user.screen_name, tweet.text])
df = pd.DataFrame(data, columns=columns)
df.to_csv('tweets.csv')
