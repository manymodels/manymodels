# RQs.md

This document lays out potential research questions (RQs) involved in the many models research program.

We currently organize RQs into a number of “layers”:

- a model layer, covering interactions between models.

- a data layer, covering sharing, transmission, integration, and management of aggregate data sets

- a world layer, covering applications, processes, and institutions through which data is generated and then published on the internet

_These layers should not be treated as a specification or architectural commitment by the research community. For the moment, they are simply ways of organizing research questions._


# Model layer

Definition: The model layer supports a set of fixed, rich interactions between pre-trained models.

Disciplines (not exclusive): AI, machine learning, transfer learning, metalearning, ensemble methods, differentiable games, computational learning theory, ML and data engineering

The broad research questions tackled at this layer are primarily concerned with statistical learning, both theoretical and empirical.


## Many models vs. one model

Say that a _mechanism for model interaction_ (or just _interaction_) is some algorithm through which two or more pre-trained input models interact in order to produce a behavior, usually a new output model or updated versions of the input models. Example interactions include transfer learning, weight sharing, synthetic data sets, and differentiable games. Under what set of interactions, assumptions, and tasks do many models perform better than one model? For example, in ensemble methods, classical results within PAC learning show that many weakly-performant classifiers can be aggregated (with AdaBoost as the interaction algorithm) to produce arbitrarily-strong classifiers.

What happens as we relax assumptions about models sharing the same data source or the same assumptions? How does performance of many models vary by task in the generative AI context? For example, suppose we focus on the natural language generation in response to natural language prompts. To what degree do old theoretical results about ensemble methods break in the LLM regime?

Related work: [Roth et al. 2023](https://dl.acm.org/doi/10.1145/3593013.3593980)

Tags: theory


## Implication of scaling laws

What are the scaling laws to training LLMs? In the context of LLMs, is there ever a point at which it makes sense (whether in terms of performance, compute, or data) to have smaller and more specialized models rather than simply adding data or spending more on compute in a large foundation model?

Tags: theory, scaling, evaluation


## Models of shared data

If a class of models are trained over overlapping data, what constraints can we impose about their possible differences in performance?

Tags: theory


## Integrating models vs. integrating data

Is it easier or cheaper to “integrate” many models trained on different data or to procure and integrate many data sets and then train one model?

Tags: model integration, data integration


## Universal mechanisms

Is there a “universal” mechanism through which models interact with each other? For an LLM, is this mechanism just natural language?

Tags: theory


## Efficiency of many models

For a given mechanism for model interaction, To what degree do any of the above mechanisms add efficiency to performance, data, or compute?

Tags: data efficiency, efficient computing


## Infrastructure for model integration

Is there some form of infrastructure that can automate or incentivize any of the above mechanisms?

Tags: infrastructure for models, incentives


## Ablation testing with circuits of models

If we connect various models together (as we might imagine a product that chains together LLMs), which components explain performance?

Tags: explaining, model composition


## Performance guarantees

To what degree do existing ensemble and adaptive learning methods deliver performance guarantees to LLMs in training or compute?

Tags: theory


## Conjectures

We also have collected some conjectures that might drive model-layer research:

- Conjecture: there exists a Zipf’s-style power law describing the relative size of models, in a “natural” distribution of models over some data set or collection of data sets.

- Conjecture: It is possible to beat scaling laws in certain contexts by hooking up distinct, separately trained models. [Can we formalize this claim?]


# Data layer

Definition: The data layer is concerned with management of aggregated records of interest. ML operators (or intermediaries in the AI supply chain) must make choices around schemas (e.g. that determines how files store information), sampling, transformations, integrations, as well as operational concerns (e.g. computing across many devices).

Disciplines (not exclusive): data integration, data set management, ML operations, data science, data mining, statistics, industrial engineering, data regulation

In terms of disciplinary boundaries, we expect many models research at the data layer to involve aspects of. The broad research question at the ata layer: how do we store and provision good data for open and decentralized modeling efforts?

Keywords: data licenses, data retention preferences, schema design, sampling, data augmentation


## Schemas

Can we change data schemas to make modeling easy for a wider variety of use cases or developer interests?

Tags: data schema


## Linked Data

Can we link datasets in a way that sets currently used for primarily a single model become useful for many upstream models?

Tags: data enrichment, data linkage


## Data storage for many models

How should data be stored so that it can be efficiently served (e.g. for training) to many models? Compare this to the kinds of efficiencies we can expect in training one model in a central datacenter or supercomputing cluster.

Tags: data storage


## Fair trade data 

Can adopting standards for “fair trade data” or “transparent data” accelerate research or increase data production?

Tags: standards, certification


## Participation in alternative data practice. 

Assuming the above questions are answered and new techniques for schemas, linkage, storage, and “fair trade”, what are the practical barriers to adoption? 

Tags: meta


# World layer

We can think of the world layer as containing the actual signals and information sources that an AI system aims to model. In short, doing research and designing “many models”-focused interventions at the world layer involves deploying new interfaces to the world and, in many cases, intervening on and engaging directly with the people and institutions who are the subject of modeling and/or the source of data.

In terms of disciplinary boundaries, we expect “many models” research at the world layer to involve components of [human-computer interaction](https://dl.acm.org/doi/10.1145/2907069), economics, sociology, organizational and behavioral sciences. Some of this research may also draw on “classical” engineering in signal processing and measurement.

In general, work that supports open data will support many models, though as we discuss below there will be important questions about balancing public (e.g. peer production) data contributions and private (e.g. online crowdwork) data contributions.

A non-exhaustive list of relevant research keywords:



* peer production
* Digital commons (see e.g. [Huang and Siddarth 2023](https://arxiv.org/pdf/2303.11074.pdf))
* web-scale data
* online communities
* computational social science

Most of the research questions in this area will fall under the broad goal of _helping people to produce data in ways that do not feed (only) into existing centralized technical infrastructures_.

 


## Models that regenerate data. 

How can we use “many models” artifacts (e.g. a hub of model weights like HuggingFace) to incentivize the creation of data that preferentially flows to open source or decentralized AI models?

Tags: data, incentives


## Regeneration and a “many models” brand

How does promoting the “many models brand” impact incentives around the creation of new data? Could we see collective organizing and peer production around efforts to specifically create data for decentralized modeling? (c.f. [OpenAssistant](https://open-assistant.io/)).

Tags: meta, data


## Capturing richer data

How can we design interfaces that help people send some subset of their digital interactions to a data commons?

Tags: data, incentives, AI commons, data commons


## Leveraging existing online platforms

Are there opportunities to get more open data from existing online platforms, with user consent? What drives platforms to adopt open data policies?

Tags: data, incentives


## Dignified data markets for many models

A world of many models will likely mean many potential data buyers. How can we create dignified markets for record creation work, avoiding the pitfalls of past online crowdwork marketplaces and balancing emerging concerns around consent?

Tags: data, data ethics, crowdsourcing, crowdwork, labor economics


## Incentives to contribute data

How can we balance existing incentives around peer production-style contributions (e.g. incentives to contribute to Wikipedia or Stack Exchange) with semi-public contributions (e.g. incentives to maintain a niche subreddit) and private, labor market-style contributions (e.g. monetary incentives to do work on Mechanical Turk or Prolific).

Tags: data, incentives, peer production, labor


# RQs not obviously in any layer


## Data value tracing

In a many models setting, how can we compute the value of a data point? Cf. the attribution problem for a single model, related to data compression-based approaches to analyzing learning. Now, suppose we wanted to compute some synthetic value for a data point based on the value of that data point attributed to many models. One could argue that a “many models” approach could provide rich, multi-dimensional values. But how do we make this work in practice?

See e.g. work on model and dataset multiplicity

Tags: data, attribution


## Many Platforms vs. Many Models

It seems reasonable to imagine that centralization of online platforms might impact the viability of many models. But does it? In other words, does decentralization of _platforms_ beget decentralization of _models_ themselves?

If I want a world of Many Models, should I invest more effort in improving Stack Exchange or creating many Stack Exchange alternatives?

Tags: meta, platform economics. 


## Many models vs. one model: research questions

What research questions are most comparatively useful for many models versus one model?

Tags: meta


## Questions about “few models”

Generally, we are comparing here the advantages of many models versus one model. However, there may be circumstances in which a “many models equilibrium” _or _a “one giant model equilibrium” could be better than few models (some low number of comparable and competitive models). What are some examples of such circumstances? Consider the question in both a theoretical statistical setting where we are just considering model performance as well as in a more practical industrial setting with economic or national actors controlling the models. Do these circumstances share any properties?

Tags: meta, industrial theory, politics, economics


# Related Work


## Work in the ML and FAccT space on model and dataset multiplicity

Emily Black, Manish Raghavan, and Solon Barocas. 2022. Model Multiplicity: Opportunities, Concerns, and Solutions. In Proceedings of the 2022 ACM Conference on Fairness, Accountability, and Transparency (FAccT '22). Association for Computing Machinery, New York, NY, USA, 850–863. [https://doi.org/10.1145/3531146.3533149](https://doi.org/10.1145/3531146.3533149) 

Aaron Roth, Alexander Tolbert, and Scott Weinstein. 2023. Reconciling Individual Probability Forecasts✱ In Proceedings of the 2023 ACM Conference on Fairness, Accountability, and Transparency (FAccT '23). Association for Computing Machinery, New York, NY, USA, 101–110. [https://doi.org/10.1145/3593013.3593980](https://doi.org/10.1145/3593013.3593980)

Anna P. Meyer, Aws Albarghouthi, and Loris D'Antoni. 2023. The Dataset Multiplicity Problem: How Unreliable Data Impacts Predictions. In Proceedings of the 2023 ACM Conference on Fairness, Accountability, and Transparency (FAccT '23). Association for Computing Machinery, New York, NY, USA, 193–204. [https://doi.org/10.1145/3593013.3593988](https://doi.org/10.1145/3593013.3593988)

Charles Marx, Flavio Calmon, Berk Ustun. 2020. Predictive Multiplicity in Classification. Proceedings of the 37th International Conference on Machine Learning, PMLR 119:6765-6774, 2020.
