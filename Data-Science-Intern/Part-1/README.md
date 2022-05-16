Challenge Link: https://docs.google.com/document/d/1JxYz-VZHIctOQcw1PIUvCuYouxDWnew5yzBhluVwbso/edit#

<h2>Solution 1</h2>
The reason of the analysis seems wrong because the analysis is done with the wrong data and wrong metrics. There are certain skewness in the dataset. 
- Average calculated is based on the order_amount and number of orders instead of order_amount and total_items sold. 
  - Solution: Scale total_items to 1 items and engineer a new feature. 
- Remove anomolies and re-evaluate the average price value: 
  - For instance, we see 17 instances of 2000 items purchased, which of
course will skew the average; we should take out shop 42.
  - As well, the average order will also be skewed because shop 78 is selling
each shoe for about $27,725; sneakers should not be this high!
  - Therefore after taking out the anomalous shops, shop 42 and 78, we get an average order value of $300, which makes sense as some customers purchase more than 1 item during their visit!

  - We also see that the average number of items purchased (after removing outliers) is about 2 items; this seems correct!

- Use new metrics:
  - Assuming we leave the anomalies in for data reasons, we can use a new
metric to track shoe affordability. As seen previously, the average is \$3145.13 because of anomalies.
  - Hence, we can use the describe() function to assist us with a new metric.
  - After seeing the metrics, we can also implement z-score to see how each transaction differs from the norm. Then, we can filter out anomalies and see what went wrong with our analysis!



<h3>Remove anomalies and re-evaluate average order value</h3>

- Following up with observation 3, it is often incorrect to judge and analyze the dataset based off
of the average. For instance, any majorly large number will skew the average. Hence, we can use percentiles (25%, median, 75%) to judge the entire dataset.
- Adding on to our .describe() function, instead of looking at affordability through the average
order amount of the total dataset, we can look at the z-score of each order, to determine if they are within the limits of a typical order. The z-score tells us the number of standard deviations away from the average, in which this feature would capture irregular values (being outside of
multiple standard deviations).
- Therefore, we now have a metric based off of the entire dataset and a metric to analyze each independent order!




<h3>Use new metrics</h3> 
- The value of using median is that we disregard anomalies, contrary to using average. Even so, we were able to get 25%, median, and 75% using the describe() function. We actually found that the 75% percentile is similar to our average. Hence, median (and percentiles) are now a better judgement of the entire dataset.
- In addition, rather than looking at the whole dataset, we can now see each individual transaction and analyze whether it is a valid measure of affordability using z-score. - After feature
engineering the standard deviation of each transaction, we can analyze when orders are anomalous, whether it be from shop 78 that is overpricing the product, or shop 42 that is selling 2000 items per transaction. Knowing that Shopify works with various businesses, we have pointed out that shop 78 and shop 42 were the reasons why our average order value is skewed,
in which there is value to using z-score.
- To summarize, one investigation turned into two metrics, using percentiles for judgement of the entire dataset, and z-score as a judgement for each independent order.

<h2>Solution 2</h2>
- Following up with observation 3, it is often incorrect to judge and analyze the dataset based off of the average. For instance, any majorly large number will skew the average. Hence, we can use percentiles (25%, median, 75%) to judge the entire dataset.
- Adding on to our .describe() function, instead of looking at affordability through the average order amount of the total dataset, we can look at the z-score of each order, to determine if they are within the limits of a typical order. 
- The z-score tells us the number of standard deviations away from the average, in which this feature would capture irregular values (being outside of multiple standard deviations).
- Therefore, we now have a metric based off of the entire dataset and a metric to analyze each
independent order!

<h2>Solution 3</h2>
- The value of using median is that we disregard anomalies, contrary to using average. Even so, we were able to get 25%, median, and 75% using the describe() function. We actually found that the 75% percentile is similar to our average. Hence, median (and percentiles) are now a
better judgement of the entire dataset.
- In addition, rather than looking at the whole dataset, we can now see each individual transaction and analyze whether it is a valid measure of affordability using z-score. After feature engineering the standard deviation of each transaction, we can analyze when orders are anomalous, whether it be from shop 78 that is overpricing the product, or shop 42 that is selling 2000 items per transaction. Knowing that Shopify works with various businesses, we have pointed out that shop 78 and shop 42 were the reasons why our average order value is skewed, in which there is value to using z-score.
- To summarize, one investigation turned into two metrics, using percentiles for judgement of the entire dataset, and z-score as a judgement for each independent order.
