# Bitcoin_price_index
**Architecture: Serverless batch insert**

![image](https://user-images.githubusercontent.com/111728805/192679919-c034bb2e-1d11-425d-88e7-96cbcf829f07.png)

**Bitcoin price API from Coindesk**

Bitcoin Price Index API: https://api.coindesk.com/v1/bpi/currentprice/THB.json

Use https://jsonformatter.org/ for make a simple format and easy to read the key-value.

![image](https://user-images.githubusercontent.com/111728805/192695497-e31bcf91-206b-4f92-9b2e-23c5011d6feb.png)

**Create Dataset in Bigquery**

![image](https://user-images.githubusercontent.com/111728805/192695559-9a954789-4ef6-4b86-8d78-63bfe295f7e5.png)

Create the destination table with the column that include the timestamp, Price_THB, and Price_USD.

![image](https://user-images.githubusercontent.com/111728805/192695730-6bca486e-7114-4f14-a600-1cc1ccbf912b.png)

**Create Cloud Functions**

Create cloud functions jobs by using Cloud Pub/Sub for trigger the message.

![image](https://user-images.githubusercontent.com/111728805/192695816-ee2a0f1e-e06d-42f0-a5db-4667267f4e3b.png)

Create new Pub/Sub topics.

![image](https://user-images.githubusercontent.com/111728805/192695877-df48f002-fc18-4472-a8ac-99b5d822143a.png)

Setting the environment variables for run the function in next steps.

![image](https://user-images.githubusercontent.com/111728805/192695919-e069f48a-6a90-4067-bd71-e3def273f311.png)

Import the code from main.py to the console.

![image](https://user-images.githubusercontent.com/111728805/192695962-cd16acc6-aeb8-4476-910d-c6af363382b6.png)

Edit the schema for competible with json files. 

![image](https://user-images.githubusercontent.com/111728805/192695994-b1453b3c-35dd-437c-bd85-aa3f2819a7b3.png)

Change the Entry point from default hellp_pubsub ==> insert_data

![image](https://user-images.githubusercontent.com/111728805/192696055-82caa3d7-a988-46b5-803d-bdfe81d7a5da.png)

Setting Cloud Scheduler for trigger the message every 5 minute with cron job.

![image](https://user-images.githubusercontent.com/111728805/192696119-ca925f13-c27c-4dba-940e-6304b1dcd0b8.png)

When finish every steps, let's see what happend on the Bigquery.

![image](https://user-images.githubusercontent.com/111728805/192696167-209e0aa8-9280-433d-b85f-21c8f208254f.png)

Now we got THB and USD Price on Bigquery. 

**reference**
*  https://github.com/fonylew/simple-cloud-functions-to-bigquery

*  https://towardsdatascience.com/how-to-upload-data-to-google-bigquery-using-python-in-3-steps-7138ae625fe3

*  https://github.com/GoogleCloudPlatform/python-docs-samples/blob/main/functions/helloworld/main.py



