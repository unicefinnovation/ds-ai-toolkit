# Model Card

Model cards are documents that provide important information about a machine learning model. The concept of a model card was [introduced by Google in 2019](https://arxiv.org/abs/1810.03993). Since then it has become best practice to provide a model card when releasing a model publicly. HuggingFace, the most popular forum for sharing models, has adopted Model Cards.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2025-08-31 at 5.04.09 PM.png" alt=""><figcaption></figcaption></figure>

As a result, potential users will be able to understand the intended use, how it was evaluated, factors that might affect the model performance, data used to train it and so on. A good model card should be tailored to its audience, which will vary based on the context, but generally is not only a technical audience but also end users. Generally a Model Card includes the following sections

* Model description
* Intended use
* Features used in the model
* Metrics
* Data used for training & evaluation
* Limitations
* Ethical Considerations

Model Cards exist to make sure that a model is not deployed in a way that is unsuitable or potentially harmful. For example, if a text classification model has been trained on legal texts it would be unsuitable to directly apply the same algorithm to social media posts and expect the same level of performance.&#x20;

The best way to understand Model Cards is to look at some examples

* [Detecting toxicity in text](https://github.com/Kaggle/learntools/blob/master/notebooks/ethics/pdfs/toxicity_in_text_model_card.pdf)
* [Smiling detection in images](https://github.com/Kaggle/learntools/blob/master/notebooks/ethics/pdfs/smiling_in_images_model_card.pdf)
