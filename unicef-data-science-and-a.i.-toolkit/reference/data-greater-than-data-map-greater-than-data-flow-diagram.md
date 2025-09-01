# Data -> Data Map -> Data Flow Diagram

Most data can be thought of as structured data in a tabular format just like an Excel spreadsheet or database table with rows of data with values in columns (images, video and text are examples of unstructured data types). What this basically means that unstructured data needs more processing to make it directly useable whereas structured data is ready for processing.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc3XqTIY2Gw92tyAJVIyHM2fXR9szDS2dMuWtwVfoOMwom_ylvrsQbCznidoplDw5af-9YxXnvRd5QOQEtVAdeU0GFmDDs91WwbU6pZPtHJm4YQ7-zAKGOUfh60gfWVdgxE6Lb84kGYnbr4dTMsiaJG9XpM?key=x7y24dvBIc283ZMkSlUx_Q" alt=""><figcaption></figcaption></figure>

_Produced by DALLE with prompt Show me an image that shows the difference between structured data and unstructured data. One side should have typical tabular data and the other unstructured data_

The data that arrives into your organisation will likely go through several stages of processing before producing an output (that output might be the prediction of an ML model or simply calculating an average or other aggregation). For example, you might filter out some outliers, join with other data or engineer some features from the raw columns. You might want to join some data together, for example if you have one dataset with the population of each municipality and another with the rainfall in each personality, then you would join them on the municipality name into one data set.

The different datasets that come into your organisation might come from different sources that update with different frequencies. For example, you might have data that your users produce that is collected in real-time, weather data that arrives hourly and prices that are set daily.

More importantly, some of your data might be sensitive, containing personal information that either identifies people directly e.g. name, social security number of equivalent or could identify them indirectly e.g. phone number, address or a combination. It is important that this kind of data is kept secure and is not exposed to other users and also that protected attributes are not used to make predictions \[see [_How should I evaluate a machine learning model to ensure fairness?_](../quick-answers-to-questions.md#how-should-i-evaluate-a-machine-learning-model-to-ensure-fairness)].&#x20;

The [Data Privacy & Security mentoring stream](https://app.gitbook.com/o/dzsBDD9SiWXEEyjPOOwx/s/8TvioEC2HyvZZAGDhtfR/) will work through producing a Data Map in more detail. For the early DS/AI mentoring sessions, a basic version of this will sufficient to get a clear picture of the data that your organisation has and will use in your product. The schemas of your tables can be extracted automatically from your databases.

A Data Flow Diagram goes one step further and considers the end to end processing of your data. All data science workflows are slightly different but typical all have some version of&#x20;

1. Collection
2. Cleaning
3. Pre-processing/feature engineering
4. Loading

It is important to be able to describe the [lineage of the data](https://atlan.com/data-lineage-explained/) to ensure that your work is reproducible by yourself if required and by others \[see [_How do I make my data science work reproducible?_](../quick-answers-to-questions.md#how-do-i-make-an-ai-model-open-source)]. For this reason the [Open Source mentoring stream](https://app.gitbook.com/o/dzsBDD9SiWXEEyjPOOwx/s/3onWpwKQoSu9x6CQsQ6F/) will cover in detail making your code theoretically and practically reproducible.

What does this mean for typical data science workflows?&#x20;

**Make notebooks deterministic**: Notebooks are great for initial explorations, but don't work well with version control and can sometimes execute out of order and have outputs that outdates. This can be fixed with discipline: moving code from notebooks to scripts regularly as they become stable. Or considering prupose built technologies such as [marimo](https://marimo.io/) which are designed around DAGs. [nbdev](https://nbdev.fast.ai/) also incorporates tests and documentation into your notebooks from the ground.
