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

### Approach for Existing users & items - Item-Item Collaborative filtering

#### Data Preparation

- First we need to record the data with following column structure:
 - User Id
 - Offer Id
 - Response code
- Response code should be represented in the following form:
 - 0 - No user-offer interaction 
 - 1 - Bad response from the user
 - 2 - Neutral response from the user
 - 3 - Good response from the user
- Once the data collected in above format, pivot the data to get User-Offer matrix with the response as the value. 

#### Item-Item Similarity matrix

Calculate the pairwise cosine similarity of each item pair and store the values in the item-item similarity matrix.

#### Make recommendation

Use the user-offer matrix and the similarity matrix to get new offers that are similar to the ones the user liked in the past. 

### Approach for new users

Since we don't have any data on a new user, we can't make similarity based recommendations. Instead, we can use one of the following:

- Recommended the most popular offers. 
- At the time of joining, ask the user for their preferences, and make offers based on that. 

Once we have enough data about the user, we can use the item-item similarity model. 

### Approach for new offers 

Without any user response data for an offer, our similarity model will not work. So, when a new offer is introduced, we can use the content of the offer and user preferences to recommend it to users. Once we have enough data, we can use the similarity model. 

### Approach for choosing Channel

The choice for channel can be done in one of the following ways:

- Ask the user for channel preference when they join.
- Run a second recommendation system that predicts which channel each user likes best.

### Effort involved

The recommendation model described above is not very complex in itself. The complexity in the above recommendation system comes from the size and type of input data. Since most of the time will be spent on gathering, storing, cleaning and preparing the data to be fed into the model, the effort involved will largely depend on data collection and data preparation phase.


