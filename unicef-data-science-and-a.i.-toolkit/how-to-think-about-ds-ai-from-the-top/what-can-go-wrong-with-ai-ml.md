# What can go Wrong with AI/ML?

To build a robust AI powered product that is in production is not easy! Here are a few common pain-points with some links to other parts of the toolkit that go into more detail about how to solve them

* **Data Availability**: your application needs to be fed data from somewhere! Data can be collected, bought or sometimes even generated. If your data is coming from a third party, especially a government organisation, it's possible that data will stop being available in the future. If you need labelled data, it can be hard to find people to do that for you.
* **Poor performance**: most AI models don't achieve good performance the first time that they are trained. There are may different reasons why; the raw data might have too many missing values, a different model might be more appropriate or the metric of 'performance' is not quite the right one. Some iteration and testing is required.&#x20;
* **Data Assumptions**: It's easy to assume (or hope!) that the data you have is the data you want or need. Often the data you have doesn't actually match our assumptions. If haven't explored your data as a first step then it's hard to know if your assumptions are correct. This will cause your downstream steps to also behave strangely.
* **Don't predict the present from the future**: AI is all about looking at past data in order to say something about the future ([data analysis](https://ischool.syracuse.edu/data-analytics-vs-data-analysis/) generally refers to looking at past data in order to extract historical trends). To measure how good an AI model is at doing this, we need to test the model on some data it has never seen before (this known as 'held-out' or a 'test set'. If we don't do this properly, we are effectively cheating and when put into production the performance will drop significantly.
* **Performance drops over time**: AI models, like all code, require maintenance. But unlike code, which can require security updates and patches, AI systems are based on code _and data_. That means that the new data that comes in and underlies the model can start to look different to the data used at the time the model was trained. For example, consumer credit card transactions will look different if there is a charge introduced for small transactions.
* **User Adoption**: An AI product, like any other product, has to solve a problem for a user! It is important to properly scope out the problem and make sure that the methods you use address the problem a user is facing. it can be easy to use data that is readily available even if it is not the best to solve the problem or to use exciting new technical methods rather than the most appropriate ones.&#x20;
* **Harmful Behaviour**: AI systems can be harmful to users or other stakeholders due to biases learned in training or poor performance. This is particularly true of Generative AI systems which tend to always produce an output even if they are unsure of the 'correct answer'.





Machine Learning Lifecycle

Part of the challenge of data science is that there are lots of different routes to get from that raw data to something that your users can be expected to easily use. In other words, data science is sometimes as much of an art as a science. What does this mean in practise?&#x20;



* Data science work is iterative
* The practise of data science can look very different across fields and sectors
* The choices to be made at each stage of the process depends heavily on the final use case
* \


It is important to bear these principles in mind.

It can be worth considering how/why DS/AI mentoring for the VF is motivated and how it differs from other mentoring streams.



* DS/AI mentoring is holistic. From the fundamental architecture storing your data all the way to how your front end appears to users, are all relevant to data science
* DS/AI has milestones along the way, but the roadmap between these needs to be defined
* The choices you make in what data you collect, how it is processed and how it is presented back to the user have many implications that need careful consideration.
* Data science involves making tradeoffs. The most accurate prediction method might be less explainable, you might need to invest some time upfront building a pipeline that will make future features easier to implement.
