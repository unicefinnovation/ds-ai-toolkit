# FAQs

<details>

<summary>What is the difference between Artificial Intelligence, Machine Learning and Data Science?</summary>

The short version is that _data science_ (DS) is the process of gathering data, making sure it is accurate and reliable and extracting useful information from it. These days, _machine learning_ (ML) and _artificial intelligence_ (AI) are used to mean the same thing, which is training a model to find patterns in data. These patterns can be used to make predictions, to classify things or to create new things.

These terms are not well defined though, so often different people use them to mean slightly different things. But in general you can think of DS as the foundation that AI is built \[see [From Data Science to AI](from-data-science-to-ai.md)]. In this toolkit I will use AI instead of ML

</details>

<details>

<summary>Why and how data science is not software engineering</summary>

Software typically starts with specific requirements, such as 'a mobile app with a landing page where users authenticate, connected to a database, that executes queries and then shows the results of the query in the app'. These requirements can be split into tickets and executed one by one.

Sometimes software engineers also take on data science tasks, especially because it can be hard to find data scientists. While there is an overlap, software engineers are more used to working towards hard requirements and might not be used to a more iterative process and discovering as you go. Likewise data scientists don't have the robust training in writing reproducble, high quality code as software engineers and might want to spend time getting a deeper understanding. In general it's very hard to find 'unicorns' people who can do everything \[see Chip Huyen [post](https://huyenchip.com/2021/09/13/data-science-infrastructure.html) on this].

Data science is a _science_ based around _data_. The _science_ part means that we are trying to discover something new which is systematic and correct. The _data_ part means that there is always some uncertainty as we never know exactly how our data will look. It is always incomplete, a sample, and any new data we collect might look different from the old data.&#x20;

This uncertainty means we might find tings we don't expect in the data and try to find new ways to deal with it. So data science is more _iterative_ than _linear_. This also applies to building AI models \[see [Machine Learning Lifecycle](../reference/machine-learning-lifecycle.md)].

</details>

<details>

<summary>When should I use Machine Learning?</summary>

It is often tempting to try to use new methodologies and technologies in your solution. But they are not always appropriate and you could end up with nasty technical debt and unpredictable behaviour. In this [great article](https://drive.google.com/file/d/1pEyizN-MhuSmqhDdEVIu8hQ1D3sjwXkH/view) about machine learning replacing human work, Erik Brynjolfson and Tom Mitchel identified these criteria.

1. _The task involves a function that maps well-defined inputs to well defined outputs_
2. _Large data sets exist or can be created containing input-output pairs_
3. _The task provides clear feedback with clearly definable goals and metrics_
4. _The task does not involve long chains of logic or reasoning that depend on diverse background knowledge or common sense_
5. _The task does not require detailed explanations for how the decision was made_
6. _The task has a tolerance for error and no need for provably correct or optimal solutions_
7. _The phenomenon or function being learned should not change rapidly over time_
8. _No specialized dexterity, physical skills, or mobility is required._

Machine learning builds on the foundation of good quality data. So #2 is critical here. It is common that

</details>

<details>

<summary>When should I use Generative AI (and when should I not)?</summary>

Generative AI (Gen AI) is very popular and it can be tempting to use Gen AI for everything. But it is important to remember it works quite differently from other kinds of AI and is better at some things than others.

* Gen AI is good for creative tasks
* Gen AI relies on knowledge in its training, it won't necessarily know anything that cannot be found by a simple web search.&#x20;
* Gen AI is only as good as it is instructed. Using vague prompts such as 'write me a business plan to make $1M a year' will not work. Instructions should be explicit. Anthropic has a [good guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) to effective prompting.
* For structured data, that is data that sits in a database table or spreadsheet, non-gen AI will be better for making predictions. Gen AI works best with unstructured data such as text, audio or video.

</details>
