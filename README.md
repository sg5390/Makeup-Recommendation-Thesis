# Makeup-Recommendation-Thesis

With superfluous amount of products in the beauty industry across the world, along with ample information on how to use them through numerous blogs or videos, it is difficult to scour through the noise while settling on one product for the customer, based on their needs. There are quite a lot of choices, options and information but the relevance of the products is an area of uncertainty [7].The customers really value their time and what they put on their skin. As a consumer, one would want to spend
 
as less time and still get the best product suited for their demographics.
While the beauty industry has progressed over the years, the technology incul- cated has really helped in shaping the industry in the past decade. We now have try on apps that use Augmented reality(AR), or smart skincare tools or printed makeup, or customization with Machine Learning and AI in skincare, fashion or hair care [9], but, surprisingly, there still lies a huge market gap when we look at the Makeup industry in particular. The gap in the market, was between finding a prod- uct via skincare articles, blog posts and knowing whether or not they should spend the money to try it out[7].
With the amount of noise in this market, it is not only difficult for consumers to understand what to pick for their needs, it is equally difficult for brands to find new ways to stand out with each brand selling same set of products with a little tweak either in formula or packaging or shade ranges. It has become important now, more than ever, to help customers find products catered to their needs. The beauty brands also want to have their users engaged at all times, which has been especially difficult due to the pandemic. Makeup recommendation systems could help users figure out what would fit their requirements.
Although there is plenty of research on product recommendation systems, there is not much work done on recommendation systems that cater to under-serving skin tones in the beauty community. In this report we present an approach that would consider the user’s skin tone, skin type and recommend the best suited products. The approach shows an accuracy of 64% while considering all the skin tones and skin types on self-scraped data set, extracted from the Sephora.
 

Introduction
1.1	Recommendation  Systems

Recommendation Systems are designed to recommend relevant customized con- tent or services to users based on different factors. The recommendations are pre- dictions that would be most liked by user based on user-item data. The predictions could be based on user’s likes, ratings or purchase history. Companies like Amazon, Netflix, YouTube utilize recommendation systems to keep their users engaged by providing with a customized product list. This has increased the scope of what user can buy since they are exposed to more products through recommendations. Since last decade, numerous firms have impacted the retail market by providing customized products to consumers based on their inputs such as StitchFix, Function of Beauty, Proven Skincare etc. All of these companies have carved a new path by addressing the gap in the market while helping users understand what is right for them. [1].
 
1.2	Working of a Recommendation System

![image](https://user-images.githubusercontent.com/56017346/121244799-518b3480-c86d-11eb-9471-0f881bbab96e.png)

Figure 1.1: Recommendation System Model


1.	Corpus Data
Consists of collection of all possible item as well as user data available at the respective websites. The data can be in millions which is input into the candidate generation block.
2.	Candidate Generation
Candidate generation filters out the content or products to hundreds based on the user’s features such as type of product, amount of money spent on an average by a user, frequency of buying a particular product. For example, the candidate generator in YouTube reduces billions of videos down to hundreds or thousands based on user’s video preferences. [6]
 
3.	Ranking
Ranking is used as a final filter to recommend the closest predictions based on user’s ratings, sentiments or dislikes. The ranking is also dependent on user as well as item features such as price of the product, brand of the product, ratings for that product. The final list is the list of products that are shown to the user as a recommended list as shown in fig 1.2.

![image](https://user-images.githubusercontent.com/56017346/121244973-7d0e1f00-c86d-11eb-9f7e-b930bfb25659.png)
    Figure 1.2: Recommendation based on Amazon purchase history!
   
![image](https://user-images.githubusercontent.com/56017346/121245114-a6c74600-c86d-11eb-9843-3a7cf68b04b0.png)
    Figure 1.3: Recommendation based on YouTube purchase history![image](https://user-images.githubusercontent.com/56017346/121245138-ac249080-c86d-11eb-8c6d-e23f713a73f2.png)


1.3	Types of Recommendation Systems!
![image](https://user-images.githubusercontent.com/56017346/121245188-bba3d980-c86d-11eb-9373-a8acb7f3a574.png)
   Figure 1.4: Types of Recommendation Systems


1.	Content based filtering

![image](https://user-images.githubusercontent.com/56017346/121245364-f279ef80-c86d-11eb-8433-87becad469d0.png)
Figure 1.5: Content Based Filtering


When it is just user based it is known as Content based filtering. We can see in fig 1.5 and calculate the dot product of the movies for each genre for this
 
given user. Movie 1 scored the highest after calculating the dot products like so
mov1 = 1.1 + 0.0 + 0.0 + 0.0 + 0.0 + 0.1 + 1.1 = 2

This means movies that are horror and are documentaries are going to be the best recommendation for this particular user based on the information of user’s watch history.
2.	Collaborative filtering
When user-item interaction is considered, it is known as Collaborative filter- ing.   We can see in the fig 1.6, the matrix on the right hand side shows the ratings given by 4 different users for 5 different items. In practical situations, recommendation systems help us fill in the missing values in this matrix, by predicting based on user-item interaction.

![image](https://user-images.githubusercontent.com/56017346/121245413-00c80b80-c86e-11eb-8dec-1c43999b312c.png)
   Figure 1.6: Collaborative Filtering
   


3.	Hybrid filtering
Hybrid filtering is a combination collaborative and content based filtering to- gether.  In this report, we get a good result with Hybrid method using KNN and Cosine Similarity.
 


Chapter 2 Related Work
![image](https://user-images.githubusercontent.com/56017346/121245512-1d644380-c86e-11eb-9c03-b657ce1fc51d.png)
Figure 2.1: Content V/S Collaborative Filtering [3]


Content based filtering seems to be good for cold start problems where we do not have history for a new user while Collaborative filtering relies on user’s history,
 
where the similarity of a user is implied based on the similar likes for a particular product as we can see in fig 2.1. Based on this information, the recommendation system can recommend a new product based on the other’s user’s likes, since these two are noted down as similar users.
There are three classic collaborative filtering approaches that are used in rec- ommendation systems such as nearest neighbor, matrix factorization and/or neural networks. We have implemented all three of them but we do not have enough re- search that caters to the under serving community in the beauty community. The approach is to find a similar products used by users in the past or find similar users who have liked the same products. The issue we will face, as we progress through the report is, how these approaches alone do not take user’s demographics into con- sideration and can end up providing a recommendation based on highest similarity but they might not fit the skin tone or skintype of the user.
In our scenario, we have to take care of two things:

1.	Cold Start problem
The idea is to help users with zero to no user-item interaction history by uti- lizing the information user put as input. In our case, we would take down the skin tone, skin type and budget as their input. This would help us find similar users of the same demographics using nearest neighbor.
2.	Products suitable for under serving skin tones
Once the products are found based on user’s input, we need to see whether the similar users liked those products or not. This will help us in identifying whether this would be good recommendation or not.
 







Chapter 3

Data Scraping and Preparation


3.1	Data acquisition

The dataset has 3749 entries and around 291 classes. A class for a product is defined as (Brandname, Productname, Shade of the product) here, which is known as PID in our table 3.1. This means we have 291 unique products based on PID(Product ID). Data acquisition was the biggest challenge in this project and took up most of the time as there were multiple web drivers that were not compatible with the Sephora website, if using python. There were no available APIs at the time and the content on website was changed twice during the course of these 8 months. We wanted information on these features from the website to be able to apply any machine learning or recommendation models on it: Brand, Product, Ingredients, Skin type, Skin tone, Reviews.
The first three were easily accessible on the main page of the website but skin
 
tone and skin type were not readily available. These two features were user based hence we had to find user data. On Sephora website, the reviews have all of the user’s data input before the actual review like skin tone, skin type, age,  shade of the product and so on.  Hence, the last three attributes had to be extracted from the review data set. Unfortunately, there were no readily available data sets for this market and had to be extracted in some certain steps. The fig 3.1 shows the idea of how we wanted our data set to finally look like.
The idea:
The data was supposed to be scraped in certain fashion and there were multiple ways of scraping the data. The following web drivers were considered before using the Selenium webdriver:
1.	Scrapy
It extracts data from the websites in a structured manner. This webdriver was chosen first because it is written in Python, so there are high chances of it being compatible with code written in Python.  The ideal dataset was supposed to be structured, making it an enticing option. But in this project, scrapy did not end up working out. Hence, this was not the ideal scraper for this project.
2.	Beautiful Soup
Beautiful Soup is another python library and is usally ideal for web scraping using XML path. Beautiful Soup returned an empty list while scraping on the Sephora website. After researching on why it returned an empty list, it was found that beautiful soup does not work well on Sephora. It worked well on Ulta and Target website but not on Sephora. So, this web scraper could not
 
be used either.

3.	Selenium
Selenium finally worked on Sephora website and returned the outputs exactly as needed. However, there were some challenges faced with the use of this web- driver. Selenium is a dynamic webdriver while Sephora is a dynamic website. Selenium also does not have a good history with Python, so that posed its own set of challenges. Selenium works best with Java. But since, Selenium was the only webdriver that returned the outputs exactly as needed, this ended up being the ideal web scraper for this project.


3.2	Data Acquisition : Challenges

1.	button.click()
The reviews needed to be loaded by clicking on the button, after the 6 reviews on that page were recorded. Hence, the button functionality was inculcated, so that it would save the manual work and time.
2.	time.sleep(10)
While scraping, the driver would skip some data from the current page, and move on to the next one. This problem is commonly known as Lazyloading. The solution to this problem was to inculcate time.sleep(5)
3.	Computation issues
There were 120 brands for blush on the website but computationally, it was
 
not possible for the system to extract over 100 reviews per product and extract 120,000 rows of data. Hence, I decided to limit the data to 35 brands and have 3500 rows of data.
4.	Limited dataset
There were 120 brands on the website for blushes. The idea was to acquire 100 reviews per brand and have in total of 12,000 rows of data. However, due to multiple time.sleep(10), it took 5 hours of continuous sitting to extract data for 33 brands.
5.	Changes made on the website
The website has changed since March and there are a few new functionalities that have been added, that are not captured in the current dataset.
After researching and analyzing Selenium webdrivers, it is safe to say that the desired dataset was acquired but it ultimately did not entirely eliminate the manual work like scrolling through the webpages. This was done so that all the data is acquired from the pages.
<img width="687" alt="Screen Shot 2021-06-08 at 3 28 50 PM" src="https://user-images.githubusercontent.com/56017346/121245633-3bca3f00-c86e-11eb-9b3d-f7e3f59883fd.png">
Table 3.1: Data extracted from the website





