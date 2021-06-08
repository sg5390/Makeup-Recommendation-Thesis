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
Figure 1.2: Recommendation based on Amazon purchase history![image](https://user-images.githubusercontent.com/56017346/121244989-81d2d300-c86d-11eb-8e9e-c769514f9329.png)


