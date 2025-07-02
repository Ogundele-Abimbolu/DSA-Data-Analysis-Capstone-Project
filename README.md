# Amazon Product and Customer Review Data Analysis

This project involved analysing a dataset of Amazon products and customer reviews to uncover valuable insights. The main goal was to understand product performance, customer sentiment, and market trends to help Amazon improve its products, refine marketing efforts, and boost customer engagement.

## 1. The Starting Point: Raw Data

Our journey began with a raw dataset named amazon.csv. This file contained a lot of information about various products, including their names, categories, prices, ratings, and the number of reviews they received.

## 2. Cleaning Up the Data: Making Sense of It All

Imagine trying to read a book where some words are misspelt, some pages are missing, and some sentences don't make sense. That's what raw data looks like. Disorganised and confusing, so before we can analyse data, we need to "clean" it. This process ensures that the data is accurate, consistent, and ready for analysis.

For this project, the cleaned data is represented in the Cleaned Data.csv file. 

# What typically happens during data cleaning:

**Handling Missing Information:** Sometimes, a product might not have a rating or a price listed. We handle these gaps by filling them in with reasonable estimates, or sometimes by removing entries if too much information is missing.

**Fixing Data Types:** Prices should be numbers so we can do calculations with them. If they were accidentally stored as text, we convert them to numbers.

**Removing Duplicates:** We check for any identical product entries that might skew our results and remove them.

**Creating New Information (Calculated Columns):** We also added new pieces of information that weren't directly in the original data but are very useful:

**Discount Percentage:** We calculated how much discount each product had by comparing its original price to its discounted price. This helps us understand pricing strategies.

**Total Potential Revenue:** This was calculated by multiplying actual_price by the rating_count. It gives us an idea of how much money a product could bring in based on its price and how many people have reviewed it (indicating popularity).

## 3. Answering Key Business Questions with Data

With my data clean and ready, I used a powerful tool called Pivot Tables and Calculated Columns to answer specific questions posed by the Amazon team. Think of a pivot table as a flexible summary tool that lets you quickly rearrange and summarise data in different ways to find patterns.

How I tackled each question and the insights I gained:

**Question 1:** What is the average discount percentage by product category?

Calculating the discount percentage per category helps Amazon understand which product categories frequently offer high discounts. It can inform pricing strategies and promotional campaigns. I was able to use a pivot table to group products by their category, and then calculated the average of the discount_percentage for each group.

Resulting file: Product Category.csv (likely contains average discount per category)

Insight: We can see which categories are most heavily discounted, which might indicate competitive pricing or clearance sales.

Question 2: How many products are listed under each category?
Why it's important: This gives Amazon an overview of its product catalogue's breadth and depth across different categories. It helps identify categories with a large or small number of offerings.

How we answered it: A pivot table was used to count the number of unique products within each category.

Resulting file: Number of Product.csv

Insight: Some categories might be very saturated with products, while others might have room for expansion.

Question 3: What is the total number of reviews per category?
Why it's important: This indicates customer engagement and popularity within each product category. Categories with more reviews generally suggest higher customer interest.

How we answered it: We summed up the rating_count for all products within each category using a pivot table.

Resulting file: Number of Reviews.csv

Insight: Categories with a high total number of reviews are likely popular and have active customer bases.

Question 4: Which products have the highest average ratings?
Why it's important: Identifying highly-rated products helps Amazon showcase its best performers and understand what customers love. These products can be highlighted in marketing.

How we answered it: We looked at the average_rating for each product and sorted them to find the top ones.

Resulting file: Highest Average Ratings.csv

Insight: Knowing the top-rated products can guide product development and marketing efforts.

Question 5: What is the average actual price vs the discounted price by category?
Why it's important: This helps Amazon analyze its pricing strategy and the impact of discounts on different product categories.

How we answered it: A pivot table was used to calculate the average actual_price and discounted_price for each category.

Resulting file: Average Vs Discounted Price.csv

Insight: We can observe the typical price difference between original and discounted prices across categories.

Question 6: Which products have the highest number of reviews?
Why it's important: Products with many reviews are often very popular and can serve as benchmarks for success. They indicate strong customer interest and potentially high sales volume.

How we answered it: We sorted products by their rating_count in descending order.

Insight: These are the "talked about" products, which can be leveraged for social proof in marketing.

Question 7: How many products have a discount of 50% or more?
Why it's important: This helps identify aggressive discounting strategies and the volume of products involved in such promotions.

How we answered it: We filtered the data to only include products where discount_percentage was 50% or higher and then counted them.

Insight: This gives a clear picture of the scale of deep discounts offered.

Question 8: What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)?
Why it's important: This provides a general understanding of overall customer satisfaction across the product range. Are most products highly rated, or are there many lower-rated ones?

How we answered it: We counted how many products fell into each rating bracket (e.g., how many had a 3.0 rating, how many had a 4.0 rating, etc.).

Resulting file: Product Ratings.csv

Insight: This shows the overall quality perception of products on the platform.

Question 9: What is the total potential revenue (actual_price × rating_count) by category?
Why it's important: This metric helps Amazon understand the revenue-generating potential of each category, considering both price and popularity.

How we answered it: We used the total_potential_revenue calculated column and then summed it up by category using a pivot table.

Resulting file: Total Potential Revenue.csv

Insight: Categories with high potential revenue should be prioritized for growth and investment.

Question 10: What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?
Why it's important: This helps Amazon understand its product offerings across different price points and identify gaps or oversaturation in certain price ranges.

How we answered it: We created "price buckets" (e.g., products under ₹200, between ₹200 and ₹500, and over ₹500) and then counted the unique products in each bucket.

Resulting file: Unique Products Per Price.csv

Insight: This helps in understanding the market segments Amazon caters to based on price.

Question 11: How does the rating relate to the level of discount?
Why it's important: This helps determine if highly discounted products tend to have lower ratings (perhaps clearing out unpopular stock) or if discounts are used to boost sales of well-rated items.

How we answered it: We analyzed the relationship between average_rating and discount_percentage. This could involve creating a scatter plot or grouping products by discount ranges and looking at their average ratings.

Insight: This can reveal patterns in how discounts are applied and their potential impact on perceived product quality.

Question 12: How many products have fewer than 1,000 reviews?
Why it's important: This helps identify products that might be new, niche, or struggling to gain traction. These products might need more visibility or marketing support.

How we answered it: We filtered the data to count products where rating_count was less than 1,000.

Insight: A large number of products with few reviews might indicate a need for more aggressive marketing or product visibility.

Question 13: Which categories have products with the highest discounts?
Why it's important: Similar to Question 1, but focusing on the highest individual discounts within categories, not just the average. This helps pinpoint specific promotional opportunities or areas where pricing might be very competitive.

How we answered it: We identified products with the highest discount_percentage and then noted their category.

Resulting file: Highest Discount.csv

Insight: This highlights categories where deep discounts are most prevalent.

Question 14: Identify the top 5 products in terms of rating and number of reviews combined.
Why it's important: This identifies the "star performers" – products that are both highly loved and very popular. These are ideal candidates for prominent display and marketing campaigns.

How we answered it: We created a combined score or ranked products based on both their average_rating and rating_count to find the top 5.

Insight: These are Amazon's strongest products in terms of customer satisfaction and engagement.

4. Visualizing the Story: The Dashboard
After analyzing all these questions, the next step was to create a Dashboard. A dashboard is like a control panel that brings all the important insights together in a visual and easy-to-understand format. Instead of looking at raw numbers, we use charts, graphs, and key performance indicators (KPIs) to tell the data's story at a glance.

The Dashboard.csv file likely contains the summarized data points and metrics that were used to build the visual dashboard. This dashboard would typically include charts showing:

Average discount by category.

Number of products per category.

Total reviews per category.

Distribution of product ratings.

Top-rated products and products with the most reviews.

Insights related to pricing and revenue potential.

This visual representation makes it much easier for Amazon's team to quickly grasp the key findings and make informed decisions without needing to dig through spreadsheets.

5. Our Suggestions for Amazon
Based on all the analysis, here are some actionable suggestions for Amazon to guide product improvement, marketing strategies, and customer engagement:

For Product Improvement:
Focus on High-Rated Products: Identify the features and qualities common among products with the highest average ratings. These insights can be used to improve other products or guide new product development.

Address Low-Rated Products: Investigate products with consistently low ratings or a high number of negative reviews. Understanding the root causes (e.g., quality issues, misleading descriptions) is crucial for improvement or discontinuation.

Monitor Review Trends: Continuously track the number and sentiment of reviews. A sudden drop in ratings or a surge in negative comments for a specific product should trigger an immediate investigation.

For Marketing Strategies:
Highlight Top Performers: Actively promote the "top 5 products in terms of rating and reviews combined." These products are proven customer favorites and can drive sales.

Strategic Discounting: Analyze the relationship between ratings and discounts. If highly discounted products tend to have lower ratings, consider if these discounts are effective or if they're just moving unpopular stock. If well-rated products are discounted, ensure these promotions are visible to maximize their impact.

Targeted Promotions: Use insights from "average discount percentage by category" and "highest discounts" to create targeted promotional campaigns for specific categories or product types.

Boost Low-Review Products: For products with fewer than 1,000 reviews, consider targeted marketing campaigns, special promotions, or encouraging early reviews to increase their visibility and customer engagement.

For Customer Engagement:
Encourage Reviews: Implement strategies to encourage more customers to leave reviews, especially for newer products or those with low review counts. This could include post-purchase emails or incentives.

Respond to Feedback: Actively monitor and respond to customer reviews, both positive and negative. This shows customers that their feedback is valued and can build trust and loyalty.

Leverage Review Content: Analyse the content of reviews to understand specific customer pain points or delights. This qualitative data is invaluable for product improvement and marketing messaging.

Conclusion
This project provided a deep dive into Amazon's product and customer review data, transforming raw numbers into clear, actionable insights. By cleaning the data, answering specific business questions with pivot tables and calculated columns, and visualising the findings in a dashboard, we've equipped Amazon with the knowledge to make data-driven decisions that can lead to better products, more effective marketing, and stronger customer relationships.
