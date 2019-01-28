---
layout: post
title: Automatic Machine Learning is Broken [writing in progress]
---

Automatic Machine Learning (AutoML) according to Wikipedia: is automating the end-to-end process of applying machine learning to real-world problems.

Typical machine learning application contains:

- Data preprocessing
- Feature extraction, engineering and selection
- Algorithm selection
- Hyperparameters optimization

A lot of steps! AutoML aims to automate them so you can spend your precious time on more challenging tasks. Sounds cool, but is it? Let's look closer ...

### Before starting - what is your problem?

Before starting your ML pipeline (automatic or manual) you need to know what are you trying to achieve. What problem are you trying to solve? Do you really need ML? This is very important. Maybe you don't need complex Machine Learning solution?

Many problems can be solved with simple statistics.

Many problems or not ML problems.

OK, you are certain that you need ML.

### Data - what, where, how?

Then, you need data!

- What data you need? Do you already have it (somewhere), or you need to buy? Do you need manual labeling?
- Where is data located and how can be accessed?
- How to combine multiple sources data? (this can be non-trivial)

Many says, above steps are the most time consuming (thus money) in building ML solution. (at least some basic ETL will be required, to run this part in production environment)

### Let's train models (easy part)

After data is prepared the autoML can be applied. In one mouse click you can train 100s or even 1000s models which are trained in parallel in the cloud. You end up with set of models, or even of ensemble of them, trained to optimize some metric with respect to some validation scheme. The best single model (heavily tuned) will be few percent better than single model with default parameters and ensemble of all your models will give you next few percent improvement. Let’s say you will end-up with up to 10-25% improvement, pretty good! Isn't it? In same cases it is a lot and can be converted into huge ROI - think of trading solutions or credits scoring tasks.

### Model complexity

But! You end up with complex model which is:

- hard to understand blackbox (yes, you can try to use AI explainers and try to explain model or its predictions)
- time needed to compute prediction can be long - in case of ensemble, you need to compute predictions from all models in the ensemble
- hard to maintain ...

### Maintenance

What do you mean by model maintenance? Well, it is not enough to train accurate and complex AI/ML model. For using ML model in production you should:

- monitor data quality and be aware of possible drifts (for example in case of NLP the language needs years to change significantly, but in case of customer data it can be days)
- monitor model predictions (model is computing predictions on completely new data, not seen in the training, no one know what will happen, even model)
- provide feedback loop - which can be used for monitoring purposes and model retraining

### The boring software

Training ML models is exciting! Building software around it - is not. The software needed for ML model to operate in production consists of:

-

Last thing. Imagine that you are using ML for customer churn prediction. Then it means that you need to write some code (script) to use model REST API. This code needs maintenance as well and probably will be part of your ETL solution.

### To conclude:

AutoML solutions can tune the model and can bring you up to 25% improvement in model accuracy - that’s for sure huge advantage
You need a lot of resources to handle ML in your company. You need to have some ETL system to extract data from many sources and prepare it for analysis, after successful building of ML pipeline, you need ETL to use ML model
AutoML solutions do not focus on better data understanding based on ML model, they do provide some insights, but I got a feeling that their main goal is to heavily tune the model. There is no call to action based on data and insights.
AutoML solutions do not focus on model maintenance in production (drifts, monitoring, feedback) - you need expert that will continuously monitor the model performance and predictions

Because of above, even if AutoML solutions are available, you still need a lot of resources (money) to successfully deploy ML to your business. What is more, the commercial AutoML solutions are pricey (50k-200k per year) so only big enterprises can afford it now. Small and medium business should wait till the technology will be more mature and therefore cheaper.
