# AI Ethics & Transparency Roadmap - Template

Mike Nolan

How do you document your machine learning development process? This guide shares transparency best practices.

This is your at a glance version of the document. Details and resources are below.

1. Milestone 1: [**Understanding the Data Flow**](ai-ethics-and-transparency-roadmap-template.md#data-flow)
   1. Data Ecosystem Map
   2. Information Sharing Protocol
2. Milestone 2: [**Understanding the Algorithm**](ai-ethics-and-transparency-roadmap-template.md#understand-algo)
   1. Dataset Structure
   2. Common Traps Mitigations
3. Milestone 3: [**Sharing the Model**](ai-ethics-and-transparency-roadmap-template.md#document-algo)
   1. Model Card Created

### Understanding Data Flow [🔗](ai-ethics-and-transparency-roadmap-template.md#data-flow) <a href="#data-flow" id="data-flow"></a>

* **Primary Goal**: Create documentation that ensures you know what data you’re using and how you plan on sharing it.

This first milestone is about initially understanding the underlying data powering your model. This is generally important for understanding the plumbing and getting an idea about privacy and implications that may arise from sharing data.

#### Outcomes [🔗](ai-ethics-and-transparency-roadmap-template.md#data-flow--outcomes) <a href="#data-flow--outcomes" id="data-flow--outcomes"></a>

* [**Data Ecosystem Map**](https://docs.google.com/document/d/18Zg2JwUDJajVDX5VU0vMijL-c9yfumeAUYDc7rgC4iQ/edit): This is to document where their data is coming from, what is using it, stakeholders, etc. The benefit here is not just helping organize how data collection will work in production but also projecting partnerships which may need to be formed in the future.
* [**Information Sharing Protocol**](https://docs.google.com/document/d/1MISHbWU7KGo4Z4AR-b222f6uXrtpQ-GJiJemGYoL--E/edit): This document is all about conducting an initial assessment of the sensitivity of information you are collecting, who you want to share it with, and how. It is fairly well-thought but is worth a review and potentially some edits. If you are in the EU, it might just be better to do a [Data Protection Impact Assessment](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/data-protection-impact-assessments-dpias/what-is-a-dpia/).

### Understanding the Algorithm [🔗](ai-ethics-and-transparency-roadmap-template.md#understand-algo) <a href="#understand-algo" id="understand-algo"></a>

* **Primary Goal**: Create documentation to ensure your whole team understand exactly how your model will be working.

A large part of this will be determining the method of managing your datasets as they evolve over the development of the program.

#### Outcomes [🔗](ai-ethics-and-transparency-roadmap-template.md#understand-algo--outcomes) <a href="#understand-algo--outcomes" id="understand-algo--outcomes"></a>

* [**Determine Dataset Structure**](https://humanitarian.atlassian.net/wiki/spaces/imtoolbox/pages/61734950/File+and+Dataset+Management): As you create new data sets, update them, and remove old datasets, you should follow an easy to follow protocol for keeping track of your various data sets as they are updated and deprecated.
* [**Common Traps When Building Models**](broken-reference): Review the following traps and document potential risks of your application falling into any of these traps.

### Documenting the Algorithm [🔗](ai-ethics-and-transparency-roadmap-template.md#document-algo) <a href="#document-algo" id="document-algo"></a>

* **Primary Goal**: Produce documentation that should be shared with the model.

#### Outcomes [🔗](ai-ethics-and-transparency-roadmap-template.md#document-algo--outcomes) <a href="#document-algo--outcomes" id="document-algo--outcomes"></a>

* [**Document Machine Learning Model Card**](broken-reference): Before you release or begin production use of your machine learning model, you can use the linked template to comprehensively document the effects, background, and purpose of your model. This will serve as a core document showing how the model makes the decision it does.

Updated on 21 Jun 2022

**Related Articles**
