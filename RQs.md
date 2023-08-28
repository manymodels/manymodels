<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 1.429 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Mon Aug 28 2023 11:39:35 GMT-0700 (PDT)
* Source doc: Content for website: Many Models
* This is a partial selection. Check to make sure intra-doc links work.
----->

# Research Questions


This document lays out potential research questions (RQs) involved in the many models research program.

We currently organize RQs into a number of “layers”:

- a model layer, covering interactions between models.

- a data layer, covering sharing, transmission, integration, and management of aggregate data sets

- a world layer, covering applications, processes, and institutions through which data is generated and then published on the internet

_These layers should not be treated as a specification or architectural commitment by the research community. For the moment, they are simply ways of organizing research questions._ 

**# Model layer**

Definition: The model layer supports a set of fixed, rich interactions between pre-trained models.

Disciplines (not exclusive): AI, machine learning, transfer learning, metalearning, ensemble methods, differentiable games, computational learning theory, ML and data engineering

The broad research questions tackled at this layer are primarily concerned with statistical learning, both theoretical and empirical.



1. **Many models vs. one model**. 
    1. Say that a _mechanism for model interaction_ (or just _interaction_) is some algorithm through which two or more pre-trained input models interact in order to produce a behavior, usually a new output model or updated versions of the input models. Example interactions include transfer learning, weight sharing, synthetic data sets, and differentiable games. Under what set of interactions, assumptions, and tasks do many models perform better than one model? For example, in ensemble methods, classical results within PAC learning show that many weakly-performant classifiers can be aggregated (with AdaBoost as the interaction algorithm) to produce arbitrarily-strong classifiers.
        1. What happens as we relax assumptions about models sharing the same data source or the same assumptions?
        2. How does performance of many models vary by task in the generative AI context? For example, suppose we focus on the natural language generation in response to natural language prompts. 
        3. To what degree do old theoretical results about ensemble methods break in the LLM regime?
    2. Tags: theory
    3. Related work: [Roth et al. 2023](https://dl.acm.org/doi/10.1145/3593013.3593980)
2. **Implication of scaling laws**. 
    4. What are the scaling laws to training LLMs? In the context of LLMs, is there ever a point at which it makes sense (whether in terms of performance, compute, or data) to have smaller and more specialized models rather than simply adding data or spending more on compute in a large foundation model?
    5. Tags: theory, scaling, evaluation
3. **Models of shared data.** 
    6. If a class of models are trained over overlapping data, what constraints can we impose about their possible differences in performance?
    7. Tags: theory
4. **Integrating models vs. integrating data**. 
    8. Is it easier or cheaper to “integrate” many models trained on different data or to procure and integrate many data sets and then train one model?
    9. Tags: model integration, data integration
5. **Universal mechanisms**. 
    10. Is there a “universal” mechanism through which models interact with each other? For an LLM, is this mechanism just natural language?
    11. Tags: theory
6. **Efficiency of many models**
    12. For a given mechanism for model interaction, To what degree do any of the above mechanisms add efficiency to performance, data, or compute?
    13. Tags: data efficiency, efficient computing
7. **Infrastructure for model integration**
    14. Is there some form of infrastructure that can automate or incentivize any of the above mechanisms?
    15. Tags: infrastructure for models, incentives
8. **Ablation testing with circuits of models**
    16. If we connect various models together (as we might imagine a product that chains together LLMs), which components explain performance?
    17. Tags: explaining, model composition
9. **Performance guarantees**
    18. To what degree do existing ensemble and adaptive learning methods deliver performance guarantees to LLMs in training or compute?
    19. Tags: theory

We also have collected some conjectures that might drive model-layer research



1. Conjecture: there exists a Zipf’s-style power law describing the relative size of models, in a “natural” distribution of models over some data set or collection of data sets.
2. Conjecture: It is possible to beat scaling laws in certain contexts by hooking up distinct, separately trained models.
    1. Can we formalize this claim?

**# Data layer**

Definition: The data layer is concerned with management of aggregated records of interest. ML operators (or intermediaries in the AI supply chain) must make choices around schemas (e.g. that determines how files store information), sampling, transformations, integrations, as well as operational concerns (e.g. computing across many devices).

In terms of disciplinary boundaries, we expect many models research at the data layer to involve aspects of data integration, data set management, ML operations.

Disciplines (not exclusive): Data science, data mining, statistics, industrial engineering, data regulation.

The broad research question that most many Models research projects at the data layer will contribute to is: how do we store and provision good data for open and decentralized modeling efforts?

A non-exhaustive list of relevant research keywords



* Data licenses
* data retention preferences
* schema design
* sampling
* data augmentation

Research questions:



10. **Schemas**
    20. Can we change data schemas to make modeling easy for a wider variety of use cases or developer interests?
    21. Tags: data schema
11. **Linked Data**
    22. Can we link datasets in a way that sets currently used for primarily a single model become useful for many upstream models?
    23. Tags: data enrichment, data linkage
12. **Data storage for many models**
    24. How should data be stored so that it can be efficiently served (e.g. for training) to many models? Compare this to the kinds of efficiencies we can expect in training one model in a central datacenter or supercomputing cluster.
    25. Tags: data storage
13. **Fair trade data **
    26. Can adopting standards for “fair trade data” or “transparent data” accelerate research or increase data production?
    27. Tags: standards, certification
14. **Participation in alternative data practice. **
    28. Assuming above questions are answered and new techniques for schemas, linkage, storage, and “fair trade”, what are the practical barriers to adoption? 
    29. Tags: meta

**# World layer**

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

 



15. **Models that regenerate data. **
    30. How can we use “many models” artifacts (e.g. a hub of model weights like HuggingFace) to incentivize the creation of data that preferentially flows to open source or decentralized AI models?
    31. Tags: data, incentives
16. **Regeneration and a “many models” brand**
    32. How does promoting the “many models brand” impact incentives around the creation of new data? Could we see collective organizing and peer production around efforts to specifically create data for decentralized modeling? (c.f. [OpenAssistant](https://open-assistant.io/)).
    33. Tags: meta, data
17. **Capturing richer data**
    34. How can we design interfaces that help people send some subset of their digital interactions to a data commons?
    35. Tags: data, incentives, AI commons, data commons
18. **Leveraging existing online platforms**
    36. Are there opportunities to get more open data from existing online platforms, with user consent? What drives platforms to adopt open data policies?
    37. Tags: data, incentives
19. **Dignified data markets for many models**
    38. A world of many models will likely mean many potential data buyers. How can we create dignified markets for record creation work, avoiding the pitfalls of past online crowdwork marketplaces and balancing emerging concerns around consent?
    39. Tags: data, data ethics, crowdsourcing, crowdwork, labor economics
20. **Incentives to contribute data**
    40. How can we balance existing incentives around peer production-style contributions (e.g. incentives to contribute to Wikipedia or Stack Exchange) with semi-public contributions (e.g. incentives to maintain a niche subreddit) and private, labor market-style contributions (e.g. monetary incentives to do work on Mechanical Turk or Prolific).
    41. Tags: data, incentives, peer production, labor

**# RQs not obviously in any layer**



21. **Data value tracing**
    42. In a many models setting, how can we compute the value of a data point? Cf. the attribution problem for a single model, related to data compression-based approaches to analyzing learning. Now, suppose we wanted to compute some synthetic value for a data point based on the value of that data point attributed to many models. One could argue that a “many models” approach could provide rich, multi-dimensional values. But how do we make this work in practice?
        4. See e.g. work on model and dataset multiplicity
    43. Tags: data, attribution
22. **Many Platforms vs. Many Models**
    44. It seems reasonable to imagine that centralization of online platforms might impact the viability of many models. But does it? In other words, does decentralization of _platforms_ beget decentralization of _models_ themselves?
        5. If I want a world of Many Models, should I invest more effort in improving Stack Exchange or creating many Stack Exchange alternatives?
    45. Tags: meta, platform economics. 
23. **Many models vs. one model: research questions**
    46. What research questions are most comparatively useful for many models versus one model?
    47. Tags: meta
24. **Questions about “few models”**
    48. Generally, we are comparing here the advantages of many models versus one model. However, there may be circumstances in which a “many models equilibrium” _or _a “one giant model equilibrium” could be better than few models (some low number of comparable and competitive models). What are some examples of such circumstances? Consider the question in both a theoretical statistical setting where we are just considering model performance as well as in a more practical industrial setting with economic or national actors controlling the models. Do these circumstances share any properties?
    49. Tags: meta, industrial theory, politics, economics