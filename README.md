# Network-Analysis-Influencers-on-Social-Media

In this project, I have performed network analysis on Social Media data, (scraped from Twitter) to develop more effective promotional strategies for a given product by reaching out to relevant influencers and also evaluate the financial impact of this analysis.

First, I have used network dataset from kaggle, where the data is organized in terms of two individuals, A and B such that the binary label represents a human judgement about which one of the two individuals is more influential. A label '1' means A is more influential than B. 0 means B is more influential than A. 

Using this dataset, performing feature engineering and employing ensemble methods, I have determined the influential factors in determining whether a particular person is an influencer or not. This was with achieved with a test set accuracy of 78% with the following results:

Some of the most indicative features of being an influencer are:

>Listed Count

>Follower Count

>Mentions Received

>Retweets Recieved

>Degree

>Betweenness

>Closeness

Followed by :

>Number of Posts

>Mentions Sent

>Following Count

>Retweets Sent

Once I had these parameters, I performed logistic regression with these predictors and obtained their weights for applying on the actual twitter data.
Also, Using the results from this model, I performed the financial impact of working with and without this analysis and compared it with the ideal model:

Consider a scenario where a retailer wants influencers to tweet its promotion for a product. If a non-influencer tweets, there is no benefit to the retailer. If an influencer tweets once, there is a 0.01% chance that his/her followers will buy one unit of a product. Assume the retailer has a profit margin of $10 per unit, and that one customer can buy only one unit. If an influencer tweets twice, the overall buying probability will be 0.015%.
Without analytics, the retailer offers $5 to each person (A and B) to tweet once. With analytics, the retailer offers $10 to those identified as influencers by the model to send two tweets each. If the model classifies an individual as a non-influencer, s/he is not selected/paid by the retailer to tweet

Net Profit with our analytical model: $ 9299682.44
Net Profit with perfect analytical model: $ 8009852.89
Net Profit without using analytics: $ 5321568.59

Note that we assume a perfect analytical model is the one that can predict influencers with 100% accuracy. This means that the model does not always select the influener as person with the most followers.

Net Profit with analytical model = Sum of followers of predicted influencers * Profit Margin * Buying Probability of tweeting twice - Cost for influencers * Number of predicted influencers

= 6236583679 * 10 * 0.00015 - 10 * 5500

= 9299875.5185

Net Profit with perfect anaytical model = Sum of followers of labeled Influencers from training data * 10 * 0.00015

= 5376568593 * 10 * 0.00015 - 10 * 5500

= 8009852.89

Net Profit without analytics = Sum of followers of all persons * Profit Margin * Buying Probability of tweeting once - Cost for each person * Number of persons

= 5376568593 * 10 * 0.0001 - 5 * 11000

= 5321568.59

Lift in Net Profit from our analytical model

= 9299875.5185 - 5321568.59

= 3978306.9285

Lift in Net Profit from our perfect analytical model

= 8009852.89 - 5321568.59

= 2688284.3

Lift in Net Profit from our analytical model is more than perfect analytical model because our model's predicted influencers have more followers than labeled influencer's followers. Since Lift in Net Profit is proportional to number of followers (refer formula), our analytical model results in higher Lift in Net Profit than perfect analytical model.

Using the analytical model is much more beneficial as we can see a positive lift in Net profit.
Scraping data from Twitter about 'austin', an retailer trying to promote Austin specific products can reach out to the most influential users in order to maximize his/her profits.

Below is the network coming from the scraped data:
<img width="749" alt="Screenshot 2023-02-19 at 9 15 03 PM" src="https://user-images.githubusercontent.com/101216624/220001693-0b63c862-b0bf-4363-adc6-463ed4d79b20.png">

We can see that the most influencial accounts are highlighted in blue in the center of the graph and they have the most nodes attached to them. We also see a few black circles which represent self-retweets and multiple small clusters at the periphery of the network.

Our top 20 influencers are:
<img width="165" alt="Screenshot 2023-02-19 at 9 18 23 PM" src="https://user-images.githubusercontent.com/101216624/220001833-d916e159-9acb-4431-8c78-b6b0ce5dbac6.png">

TheNBACentral: This Twitter account is popular among basketball fans in Austin, providing news and analysis on the National Basketball Association.

KXAN_News: This is the official Twitter account of KXAN-TV, the NBC affiliate in Austin, providing local news, weather, and traffic updates.

KVUE: This is the official Twitter account of KVUE-TV, the ABC affiliate in Austin, providing local news, weather, and traffic updates.

Asmongold: This Twitter account belongs to a popular Twitch streamer and YouTuber who is based in Austin and focuses on World of Warcraft content.

Austin_Police: This is the official Twitter account of the Austin Police Department, providing updates on local law enforcement activity and community outreach.

TexasTribune: This Twitter account belongs to a non-profit, non-partisan news organization that covers Texas politics and policy.

2000s_WWE: This Twitter account provides news and analysis on the World Wrestling Entertainment (WWE) events of the 2000s.

CreationEnt: This Twitter account belongs to a leading independent entertainment company that provides high-quality live events in Austin and other cities.

statesman: This Twitter account belongs to the Austin American-Statesman, the largest daily newspaper in Austin, providing local news and analysis.

austin_visual: This Twitter account showcases the visual arts scene in Austin, including exhibitions, events, and artist profiles.

thedailybeast: This Twitter account belongs to The Daily Beast, a news and opinion website that covers national and international news.

KXAN_Weather: This is the official Twitter account of the weather team at KXAN-TV, providing up-to-date weather forecasts for Austin and surrounding areas.

EvilMopacATX: This Twitter account provides commentary and satire on local Austin issues and events.

fox7austin: This is the official Twitter account of FOX 7 Austin, providing local news, weather, and traffic updates.

tplohetski: This Twitter account belongs to Tony Plohetski, an investigative reporter at the Austin American-Statesman.

BrandonHuffman: This Twitter account belongs to Brandon Huffman, a journalist and editor who covers high school and college football.

spann: This Twitter account belongs to James Spann, a well-known meteorologist and weather forecaster based in Austin.

Austin_Federa: This Twitter account provides news and analysis on the Austin chapter of the Federal Reserve Bank of Dallas.

mattlargey: This Twitter account belongs to Matt Largey, a journalist and radio host based in Austin.

TCEA: This Twitter account belongs to the Texas Computer Education Association, a professional organization that supports technology education in Texas.

We see that news channels like KXAN News, KVUE, the daily beast, texas tribune, fox 7 austin, are among the top 20 influencers in Austin. Among the top 20 we also have "tplohetski" is a news reporter and "spann" is a meterologist. This is expected as with the current winter storm, these channel received a lot retweets on the updates that they shared. UT Police and KXAN_weather has sent out multiple tweets regarding the winter storm and resources for citizens and this is being publicised among the community by other users. We also see some popular sports entity among our top 20 like The NBA Central and 2000s_WWE.

