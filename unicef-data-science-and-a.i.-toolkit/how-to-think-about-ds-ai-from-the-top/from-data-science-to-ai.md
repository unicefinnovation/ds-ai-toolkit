---
hidden: true
---

# From Data Science to AI

It might start to look like the data scientist needs to be involved in everything! In fact, part of the challenge of doing data science well is that it is hard to know where it starts and ends. There are relevant considerations all the way from the initial problem statement, through to how your software and databases are designed all the way through to the front-end that the user sees. So it is important that if your data scientist cannot be involved in all of those meetings and conversations, that you have a technical product manager or CTO who can keep a high level view of the product as a whole.

It is important to note that data science is not software engineering and data scientists are not software engineers (although it’s possible for one to sometimes do the job of the other) \[Link: why data science is not software engineering]. Software engineering usually starts from very specific requirements that get broken down into small pieces of code that are put together. Data science is harder to define from the beginning in the same way. This is mainly because data is unpredictable! The data for tomorrow won’t necessarily look like the data for today. That is why it is important to have a stage of Exploratory Data Analysis or EDA \[LINK to EDA].

However, in common with software engineering, data science and machine learning also creates ‘technical debt’ - by which we mean you have code or systems that over time will need to be maintained and fixed so that they continue to operate as they are supposed to and can be built upon \[LINK to machine learning as tech debt [paper](http://research.google/pubs/machine-learning-the-high-interest-credit-card-of-technical-debt/) from Google]. However there are subtle differences as new data recently generated can differ from old data in subtle and unexpected ways that cannot be caught by a simple unit test \[LINK Why DS is not SWE].

It is common for data science products to start with a Proof of Concept based on an open dataset. For example [Kaggle](https://www.kaggle.com/datasets) and [HuggingFace](https://huggingface.co/datasets) host lots of open datasets from all kinds of sources. These are free and open to download and experiment with. Let’s imagine that you have downloaded [this dataset](https://www.kaggle.com/datasets/amykzhang/bergen-bike-sharing-dataset-2023) of rental bicycle journeys in Bergen. You want to see if it is possible to predict the number of journeys from station A to station B given the weather and time of day. You start by exploring your data and seeing if any cleaning needs to be done. Next you choose a simple linear model that takes into account the distance between two stations and whether it is raining on a given day (simply yes or no).&#x20;

Remember that the main challenge in machine learning is to be able to generalise. What this means is that your model should be able to reliably make predictions in situations that it has not seen before; predicting the past is not very useful!

With an ‘offline’ dataset like this, the best you can do is to split your data in separate parts for training and testing. The model learns from the training data but never sees the test data until it tries to make new predictions. The model is evaluated based on the predictions it makes on the test data. Your linear model is able to predict the number of bicycle journeys to an accuracy of +/- 10 rides on average.

Now imagine what happens if the price of renting the bikes goes down? You would expect that more journeys would be made, and so the model you have trained would probably not perform as well as before. This is an example of ‘data drift’. Data drift is not always so obvious, it could be that instead of a sudden change in the conditions that the data is recorded that the data changes slowly over time. In this case that could be that people learn to love cycling so much that they buy their own bikes and rental numbers go down. The way to combat data drift is to collect new data and to retrain the model on that data to make sure it is up to date. Our academic case study would show that it is possible to predict bicycle rental numbers but it would struggle to generalise into the future.

Building data science products and putting them into production has its own considerations. (Production here means that the product is ‘live’ and public for a user to use on an ongoing basis, rather than a demo running from your own laptop or just for your team to test). It is important to go from the mindset of a ‘one time’ analysis to maintaining a reliable ongoing service. This is described by the Machine Learning Lifecycle \[LINK to Machine Learning Lifecycle]

Note another difference here between data science and software engineering. Most bugs in software are fairly obvious; a ‘Error 404 - webpage not found’ or a blue screen. But when ingesting live data and applying a model that makes some subtle assumptions to output an answer, the model could give out an answer that is not obviously ‘incorrect’. You can extend the idea of sanitising user input to other data. For example, if a web form asks a user to input their telephone number, the form can check if the number has the correct number of digits and is in the correct format. Likewise, if your model outputs a predicted value 100x larger than anything seen before you can be sure that something has gone wrong.\


\[LINK What is the difference between AI, ML and DS?]

A good and responsible data scientist will also be thinking about how any sensitive data is used from the beginning; not just when something goes wrong! \[LINK to VF mentoring process]

##
