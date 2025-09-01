---
description: Practical tips for when you are working
---

# Quick Answers to Questions

## Expandable blocks

<details>

<summary>How should I evaluate a Machine Learning model to ensure fairness?</summary>

[https://github.com/tensorflow/fairness-indicators](https://github.com/tensorflow/fairness-indicators)



[https://en.wikipedia.org/wiki/Fairness\_(machine\_learning)#Bias\_mitigation\_strategies](https://en.wikipedia.org/wiki/Fairness_\(machine_learning\)#Bias_mitigation_strategies)

</details>

<details>

<summary>Am I Doing Machine Learning?</summary>

Possibly not, and that's OK! Technically, very simple modeling like fitting a linear regression is Machine Learning. You might, however, be simply counting things and displaying that information. That might be extremely useful but isn't machine learning.

</details>

<details>

<summary>What do I do if my data is sensitive?</summary>

Much of the data that we are interested in is _personal data_ i.e. it has information about people or could be used to identify people e.g. telephone numbers. Some personal data is sensitive as it might have information that could be used to discriminate against someone e.g. medical history, gender. Most important is to follow the advice of the [Data Privacy and Security mentor](https://app.gitbook.com/o/dzsBDD9SiWXEEyjPOOwx/s/8TvioEC2HyvZZAGDhtfR/) in following appropriate laws in your jurisdiction and make sure access is properly controlled.

Personal data can be [hashed](https://www.termsfeed.com/blog/privacy-data-hashing/) to ensure safety or noise added to ensure [differential privacy](https://en.wikipedia.org/wiki/Differential_privacy) guarantees.

If you wish to use such data for modeling, there are some specific considerations. A model should not make use a protected characteristic to make a prediction to ensure fairness.

</details>

<details>

<summary>Why do I have missing data?</summary>

Missing values can occur for several reasons including structural deficiencies in the data (namely, deliberate omission in the data collection or data generating process), random occurrences, or specific reasons.

A structural deficiency would be the case of a missing component of a predictor omitted from the data. Typically, these cases could be resolved once the necessary component is identified. For example, if a hypothetical dataset has some predictor variable where values are either “A” or “B” or missing, where most values are missing, it may be tempting to discard the predictor variable due to the high rate of missingness. However, discarding this predictor variable may inadvertently be throwing away valuable information since missing can be interpreted to mean not being “A” or “B”. A better recording of the predictor variable may be to replace the missing values with “Not A or B”.

Another reason for missing values may be due to random occurrences. This can be occurrences missing completely at random (“MCAR”) where the likelihood of a missing value is equal for all data points, both observed and unobserved. Missing values can be interpreted here as independent of the data generating process. This can also be an occurrence missing at random (“MAR”) where the likelihood of a missing value is not equal for all data points. In this case, the probability of a missing value depends on the observed data, but not unobserved data.

A third reason for missingness can be due to specific reasons or missing not at random (“MNAR”). This often occurs in cross-sectional time series data where the same unit of observation (for example, patient in medical trial) drops out of a study. Measurements for this unit of observation will stop after dropping out of the study. The MNAR cases are difficult to handle in practice and data practitioners should seek to understand the nature of the missingness before applying a technique to correct for missingness since a misdiagnosis of missingness could lead to bias in model inference.

</details>

<details>

<summary>What if I have missing data?</summary>

It is very common that some rows in your tabular data will have missing values in some columns. In fact this issue is so common that there are libraries explicitly to help you deal with these such as [missingno](https://github.com/ResidentMario/missingno).

There are a few different strategies\


1. The simplest way to deal with these is simply to exclude these rows from your downstream analysis. If these rows represent a small proportion e.g. <5% of your total dataset, then this will likely be fine.
2. Missing values can be imputed: filling these missing values in with the average value of a numerical column observed in the other non-missing rows (or the most common value in a categorical column)
3. Turn the missing values into a feature. It is possible to use the information that a value is missing and turn it into a feature that can be used for a model to learn from. If you suspect that values are not missing at random and the fact that data is missing carries some information, then this will be the preferred strategy \[[Quora: How to deal with missing values](https://www.quora.com/How-can-I-deal-with-missing-values-in-a-predictive-model/answer/Claudia-Perlich?ch=10\&oid=30917299\&share=569f82a1\&srid=O95r\&target_type=answer)].

| Feature\_1 | Feature\_2 | Feature\_3 | Feature\_3\_missing |
| ---------- | ---------- | ---------- | ------------------- |
| 0.1        | 10         | \<missing> | 1                   |
| 0.15       | 7          | 11.5       | 0                   |
| 0.0        | 7          | \<missing> | 1                   |

</details>

<details>

<summary>What if I don’t have the data I want?</summary>

Data is valuable and the right data for your project is even more valuable. What you can achieve will be limited by the data that you can access and so it is very important to consider this carefully as you begin scoping your project. If you find the data you need for your solution is not available, then you might need to go back and iteratively adjust your solution.

It might be that you can find a static dataset for building a Proof of Concept but would not be sustainable for a live product. Using data that is different to your use case could also introduce subtle biases. Therefore it is recommended to consider possible contingencies.

Broadly speaking, the data you can use comes from several different categories.

**Public data**: government organisations often release data that can be relevant. Remember that often this is often provided in a format, such as a PDF, where the data needs to be extracted. Also the format can change over time. Some bigger, international organisations such as NORAD or Meta release geospatial data publicly. Some data such as Open Street Maps is both high quality and explicitly open source.&#x20;

**Paid data providers**: it is often possible to buy high quality data from providers, for example The Weather Channel or Google Maps. However, can be expensive and it will have implications for the accessibility and reproducibility of your solution.

**Data collected yourself**: it is possible to ‘scrape’ data from online sources that are not readily made available. For example, if a service has a website that displays daily prices but does not provide an API for easy data collection, you could write a program that navigates to that page each day and extracts and records the prices from that page. A few things could go wrong with this, for example you could get blocked if you make too many requests making the data unreliable or the structure of the page could change generating technical debt. There could also be legal or ethical considerations.

**Data generated by your users**: if you provide a service to users and they create data in the course of doing that, you can provide additional valuable features to those users based on this data.&#x20;

**Synthetic data**: it’s possible to create data based on a model. For example a Large Language Model like chatGPT can create text for you. This could be useful for testing your data pipeline or as a replacement for sensitive data that you want to control carefully.

</details>

<details>

<summary>What if I don’t have tagged/annotated data?</summary>

Most Machine learning models are supervised and need examples to learn from; known as the training process. LLMs can make predictions without examples, known as 'zero shot learning' but generally perform better with examples.&#x20;

If the model is being trained to predict disease from medical images, then the model will need a dataset of images and a tag or annotation of whether that image shows the disease or not. For some prediction problems, such as predicting rainfall the next day, you don’t need to tag your data. You can just wait one day and measure the rainfall.

Tagged data is very valuable and can take considerable time and money. There are online platforms where you can pay people to tag data for you. Some are general such as Amazon Mechanical Turk and others are focused on tagging images such as [Roboflow](https://roboflow.com/annotate). You will need to consider if users need specific domain knowledge to tag the images; medical images would need someone with medical knowledge for example.

Initially you and your team might need to tag some images yourself to begin training a model. A more sustainable, long term approach is to have users tag data themselves as part of their regular use of your platform. It is not immediately obvious, but by sorting your emails into folders in your inbox you are tagging emails that could be used for a classification algorithm later on.

</details>

<details>

<summary>Where to find DS/AI guidance online?</summary>

The good news is that there is a lot of information on how to do things and solve problems online.&#x20;

**StackOverflow** focuses on issues when doing software development but also data science. [StatsExchange](https://stats.stackexchange.com/) has the same format but focuses more on statistics and machine learning.

[**HuggingFace**](https://huggingface.co/) is a community for sharing ML models, datasets and knowledge.&#x20;

**Technical Blogs** Many companies have separate blogs covering how they developed their data science features, for example&#x20;

* HelloFresh: [Rethinking Customer Lifetime Value using Machine Learning at Hellofresh](https://engineering.hellofresh.com/rethinking-customer-lifetime-value-using-machine-learning-at-hellofresh-208f35eadcda)
* LinkedIn: [Musings on building a Generative AI Product](https://www.linkedin.com/blog/engineering/generative-ai/musings-on-building-a-generative-ai-product)

Discord

**Reddit** there are several subreddits that are relevant e.g. [r/deeplearning](https://www.reddit.com/r/deeplearning/), [r/localLlama](https://www.reddit.com/r/LocalLLaMA/), [r/datascience](https://www.reddit.com/r/datascience/)

**Software documentation** The very mature libraries with good open source communities have good documentation. This can be a great way to learn about the features and parameters. For example scikit-learn has a lot of guided examples for common tasks like [clustering](https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_digits.html#sphx-glr-auto-examples-cluster-plot-kmeans-digits-py).

**Online Courses** Coursera has a lot of introductory and intermediate level courses for free. For more advanced usage, fast.ai has great in depth courses on advanced topics such as stable diffusion.

Conferences There are great conferences on data science and AI, many of which record the talks and make them available. Check out the [PyData channel](https://www.youtube.com/@PyDataTV) on YouTube.

</details>

<details>

<summary>How data science for VF is different to data science in industry</summary>

The Venture Fund exists to ensure that the next generation of technology works for the most vulnerable. This means making solutions open source and deploying responsibly.

**Inclusivity**: a commercial application attempts to define a market and provide a service to the potential users in that market. Who is included in that market is a commercial question. Products for social applications should aim to be as inclusive as possible, this does not mean that the market should be ‘everyone’, rather that minority groups or protected groups should not be excluded from using your product.

**Open Source**: your solution should be open to others to build upon and should not tie users to prorietary services. The [Open Source mentoring stream](https://app.gitbook.com/o/dzsBDD9SiWXEEyjPOOwx/s/3onWpwKQoSu9x6CQsQ6F/) covers this in more detail.

</details>

<details>

<summary>Why and how AI is now Quite like Software engineering</summary>

When data science first became established, it was a very academic discipline. Only a few people knew how to do the fundamental things needed. For example Andrew Ng described implementing matrix multiplication from scratch. Previously data platforms had to be designed from the ground up. There is now much greater expectation that models should be deployed more quickly and easily.

Cloud computing has made it much easier to quickly deploy models. Hugging Face and other platforms have made it easier to find models. Open source ode libraries are very mature and have good documentation. All of this makes it much easier to deploy things without having to worry so much about the fundamentals.

This is especially true of massive models such as LLMs which need huge amounts of training. The development of these models has essentially been outsourced to a few large companies with enough resources and they are consumed as a service.

This all makes the practise of deploying AI closer to a software engineering process where an architecture must be designed and multiple services must be connected together and monitored.

</details>

<details>

<summary>What is EDA and why do we need to do it?</summary>

Exploratory Data Analysis (EDA) is a very important early step in the DS/AI lifecycle. It involves ‘getting a feel’ for your data. It is very likely that your data will contain some surprises that you don’t expect! This could be missing values, unexpected values, a change in format over time or something else. If you attempt to build your pipeline or machine learning model based on your data with conducting EDA, it is very likely that you will get errors at a later stage or misleading results based on assumptions on your data that are not correct. Your EDA will inform what cleaning steps you need to take.

EDA typically includes the following

1. Checking for missing values. Most datasets have some missing values that can be either dropped or filled in; ‘imputed’.
2. Looking at the distributions of the columns with a histogram to see if there are outliers or a small number of values repeated many times.
3. Are there duplicate rows that need to be removed?
4. Drilling down into specific records in the data to ask; do these look how you would expect? Can we start to understand the process that generated and recorded this data? Do you need a data dictionary or some more information to know what the data represents?

</details>

<details>

<summary>How do I make an AI model open source?</summary>

AI models developed by Venture Fund companies should be open-sourced, where possible, just the same as software. It is important to note that DPG certification is not always exactly the same as being 'open source'. In general, the Venture Fund follows the Open Source Institute's [definition](https://opensource.org/ai) of an open AI model.&#x20;

</details>

<details>

<summary>How do I make my data science work reproducible?</summary>

Data science has a bad reputation for not following good practices in software engineering such as version control, clean code and reproducibility. This is more of a problem as data science pipelines become more complex and integrated.&#x20;

Data science code is no different to regular code in that it should be representable as a DAG \[see [Data Maps](reference/data-greater-than-data-map-greater-than-data-flow-diagram.md)] but differs in that the requirements might not be so clear at the beginning.

The good news is that there are some tools to help us.

The main principles are the following

* Make sure all your data transformations, from the very first raw files, are captured in code. Initial pre-processing in Excel/grep/etc are prohibited!
* Transition exploratory code in notebooks to modularised code in scripts as your work matures.

[Data Science Cookie cutter](https://cookiecutter-data-science.drivendata.org/)

[Marimo](https://marimo.io/)

</details>

