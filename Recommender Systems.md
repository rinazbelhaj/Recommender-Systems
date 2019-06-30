# Recommendation System

A recommender system or a recommendation system is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item. They are primarily used in commercial applications. A recommendation engine filters the data using different algorithms and recommends the most relevant items to users. It first captures the past behavior of a customer and based on that, recommends products which the users might be likely to buy.

Recommender systems are utilized in a variety of areas, and are most commonly recognized as playlist generators for video and music services like Netflix, YouTube and Spotify, product recommenders for services such as Amazon, or content recommenders for social media platforms such as Facebook and Twitter.

# Types of Recommendation Engine

Recommendation systems use a number of different technologies. We can classify these systems into two broad groups
1. Content Based Recommendations
2. Collaborative Filtering

## 1. Content Based Recommendations :

Content-based filtering methods are based on a description of the item and a profile of the user’s preferences. These methods are best suited to situations where there is known data on an item (name, location, description, etc.), but not on the user. Content-based recommenders treat recommendation as a user-specific classification problem and learn a classifier for the user's likes and dislikes based on product features.
 
 ### Properties :
 * Idea: If you like an item then you will also like a "similar" item
 * Based on similarity of the items being recommended
 * It generally works well when its easy to determine the context/properties of each item. For instance when we are recommending the same kind of item like a movie recommendation or song recommendation
 
 ### Pros :
 * No need for data on other users
 * Able to recommend to users with unique tastes
 * Able to recommend new and unpopular items
 * Explanations for recommended items - features that caused the item to be recommended
 
 ### Cons :
 * Finding the appropriate features is hard
   * Eg: images, movies, music
 * Overspecialization
   * Never recommends items outside user's content profile
   * People might have multiple interests
   * Unable to exploit quality judgement of other users
 * Cold-start problem for new users
   * How to build a user profile ?
 
## 2. Collaborative Filtering :

Collaborative filtering is based on the assumption that people who agreed in the past will agree in the future, and that they will like similar kinds of items as they liked in the past. The system generates recommendations using only information about rating profiles for different users or items.

### Properties :
* Idea: If a person A likes item 1, 2, 3 and B like 2,3,4 then they have similar interests and A should like item 4 and B should like item 1.
* This algorithm is entirely based on the past behavior and not on the context. This makes it one of the most commonly used algorithm as it is not dependent on any additional information.
* For instance: product recommendations by e-commerce player like Amazon and merchant recommendations by banks like American Express.
* Further, there are several types of collaborative filtering algorithms :
  * **User-User Collaborative filtering:** Here we find look alike customers (based on similarity) and offer products which first customer’s look alike has chosen in past. This algorithm is very effective but takes a lot of time and resources. It requires to compute every customer pair information which takes time. Therefore, for big base platforms, this algorithm is hard to implement without a very strong parallelizable system.
  * **Item-Item Collaborative filtering:** It is quite similar to previous algorithm, but instead of finding customer look alike, we try finding item look alike. Once we have item look alike matrix, we can easily recommend alike items to customer who have purchased any item from the store. This algorithm is far less resource consuming than user-user collaborative filtering. Hence, for a new customer the algorithm takes far lesser time than user-user collaborate as we don’t need all similarity scores between customers. And with fixed number of products, product-product look alike matrix is fixed over time.

 ### Pros :
 * Works for any kind of item
   * No feature selection needed
 
 ### Cons :
 * Cold start problem
   * Need enough users in the system to find a match
 * Sparsity
   * The user/ratings matrix is sparse
   * Hard to find users that have rated the same items
 * First rater problem
   * Cannot recommend an unrated item - New items, Esoteric items
 * Popularity bias
   * Tends to recommend popular items
