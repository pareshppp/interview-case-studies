# Case Study - Marketing Campaign Recommendation System

## Background

A leading telecommunication company, ABC Telecommunications, targets its customer base via several channels – email, SMS and Social Media. They have several different campaigns that they routinely send to their customers through these channels. These offers are to cross sell a kind of service, up sell to a bigger pack, discounts and other value added services to retain customers etc.  

They have all past campaign information at a customer level – what campaign was sent, how many were sent, what was the response to each campaign etc.  

The analytics team at ABC Telecom has received a new mandate from the CMO. They are required to develop a 'smart' targeting engine. They are required to make recommendations regarding which campaign should be sent at a customer level and develop new offers since the CMO is no longer interested in mass marketing.  

## Objectives

- Develop solution framework for the recommendation engine for offers that will be sent at an individual through the various channels. These should be personalized offers that should yield maximum returns for the company. The engine should also recommend what channel to use for each instance of sending the offer. Talk about both analytics and technology in your framework of developing this recommendation engine.
- How do you develop new offers to be sent to customers that do not currently exist? How can recommendation engine suggest that to you?
- Feel free to make as many assumptions you may want to make, and list them clearly.
- Please share an approach note on how the recommendation engine framework will look like along with your estimate of effort involved in developing it.

## Report

### Assumptions

We are making the folowing assumptions about the company:

- The company has a very large user base.
- The company values the financial returns from the recommendations more than their model explainability.
- 

### Types of Recommendation systems

Listed below are a few types of recommendation systems currently used. Lets look at their applicability to this case.

- **Popularity based recommendation**
 - Recommends the most popular items to the users.
 - Similar to the mass marketing the company currently does.
 - Not a viable approach for 'smart' targeting.
- **Content/Attribute based recommendaion**
 - Recommendations based on hisorical user information.
 - Viable approach as it suggests recommendationns at an individual level.
 - But it's not super personalized or smart.
- **User-User Collaborative filtering**
 - Calculate similarity between users based on their response to different offers. Create new offers based on user-user similarity.
 - Becomes very difficult to scale as user count increases.
 - Not viable given the large customer base of the company.
- **Item-Item Collaborative filtering**
 - Calculate similarity between items/offers based on the response recieved from different users. Suggest the offer to more users based on item-item similarity.
 - Viable approach as it scales well.
 - With the knowledge of similar items/offers, the company can create new bundled package offers.
- **Model based Collaborative filtering**
 - Train embedding vectors for each user and item.
 - Use vector embeddings of users and items to predict response of user to a particular item/offer.
 - Advantage - Hyper personalized recommendation
 - Disadvantage - Black box implementation. We have no idea why a certain recommendation is made.

### Approach


