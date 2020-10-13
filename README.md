# Music Box Churn Prediction and Recommendation (Spark)
====
The idea is to predict user churn rate based on users' previous activities.


### Data 
Data of music box can be accessed from the [link](https://bittigermusicplayerdata.s3-us-west-2.amazonaws.com/list.html). 

### Install spark with ipython notebook
	* Mac
		https://gist.github.com/ololobus/4c221a0891775eaa86b0
		Take "Alternatively" approach if you want to use Spark with Jupyter Notebook
	* Linux (e.g. VM)
		https://blog.sicara.com/get-started-pyspark-jupyter-guide-tutorial-ae2fe84f594f

	* Cloud
		 Data Bricks Community Edition
		https://databricks.com/try-databricks

	* Spark Reference

		Spark ML Programming Guide
		https://spark.apache.org/docs/latest/sql-programming-guide.html

		Spark SQL Programming Guide
		https://spark.apache.org/docs/latest/ml-guide.html

		Spark API Documentation
		http://spark.apache.org/docs/latest/api/python/index.html

		Spark SQL API Documentation
		http://spark.apache.org/docs/latest/api/python/pyspark.sql.html
		

### Data Processing 
	* Remove bots and outliers
		Calculate 99 percent of play counts threshold of each user and remove those records with play counts number over threshold.
	* Down-sampling at the user level. 
		Get all distinct user_ids, down-sample user_ids and put into set, then pass data and only keep users if they are in the set. 


### Feature Engineering
	* Generate Churn Label
		Inactive users in fixed window are marked as 1, active users marked as 0.
	* Generate Churn Features
		* User Activities
			* Frequency
			* Recency
			* Total Play Time 
			* Play Time Percentage
			* Count of songs played over 80 percent of song length
		* User Profiles
			* User Device
	
### Train Model (Supervised Methods)
	* Logistic Regression
	* Random Forest
	* GBDT
	
	


