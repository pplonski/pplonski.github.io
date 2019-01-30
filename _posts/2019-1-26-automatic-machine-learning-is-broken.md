---
layout: post
title: Automatic Machine Learning is broken
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

Many problems are not ML problems. They can be optimization problems or exploratory data analysis tasks.

OK, you are certain that you need ML.

### Data - what, where, how?

Then, you need data!

- What data do you need? Do you already have it (somewhere), or you need to buy? Do you need manual labeling?
- Where is data located and how can be accessed?
- How to combine multiple sources data? (this can be non-trivial)

Many says, above steps are the most time consuming (thus money expensive) in building ML solution. (at least some basic ETL will be required, to run this part in production environment)

### Let's train models (easy part, the autoML part)

After data is prepared the autoML can be applied. In one mouse click you can train 100s or even 1000s models which are trained in parallel in the cloud. You end up with set of models, or even ensemble of them, trained to optimize some metric with respect to some validation scheme. The best single model (heavily tuned) will be few percent better than single model with default parameters and ensemble of all your models will give you next few percent improvement. Let’s say you will end-up with up to 10-25% improvement, pretty good! Isn't it? In same cases it is a lot and can be converted into huge ROI - think of trading solutions or credits scoring tasks.

### Model complexity

But! You end up with complex model which is:

- hard to understand blackbox (yes, you can try to use AI explainers and try to explain model or its predictions)
- time needed to compute prediction can be long - in case of ensemble, you need to compute predictions from all models in the ensemble
- hard to maintain ...

### Maintenance

What do you mean by model maintenance? Well, it is not enough to train accurate and fancy AI/ML model. For using ML model in production you should:

- monitor data quality and be aware of possible drifts (for example in case of NLP the language needs years to change significantly, but in case of customer data it can be days)
- monitor predictions (model is computing predictions on completely new data, not seen in the training, no one know what will happen, even model)
- provide feedback loop - which can be used for monitoring purposes and model retraining

### The boring software

Training ML models is exciting! This is what tiggers like the most! Building software around ML is not as excited. The boring software needed for ML model to operate in production consists of:

- software to prepare input data for training and production - your ETL solution
- software for serving ML model, monitoring its and data quality, and feedback loop
- software for requesting ML model to compute predictions on new data records and making actions (yes, you need to do something with predictions and you need code for it as well)

When running ML locally, last two steps are usually connected. The all used software needs some maintenance as well.

### What to do with predictions

You were successful with all above steps. Congratulations! You can compute predictions for your new data records. What to do with them?

- You can use them to get insights (I think, this is the easiest way and in fact it is not using ML model at all, it is exploratory data analysis)
- You can use them to make actions. Here are many possibilities, for example it can be submitting a trade on exchange or sending email to the customer. I think this is the most beautiful part of whole ML pipeline. **Act based on data**

### Conclusions:

1. AutoML solutions can tune the ML model and bring improvement in accuracy under some validation schema and data. It can save a lot of time required for Data Scientist to check different algorithms and validations (you dont need to code, check libraries versions, interfaces). For sure, having autoML is a huge advantage and is needed. However, in my opinion you need a lot of resources (money, time, people) to handle ML in your company, even if you have autoML magic box.
2. You need to provide a lot of **boring software** for manipulating the data and making use of ML predictions. I think this part of ML pipeline is so underrated while it **is a work-horse of data-driven solution**.
3. What is more, many times you don't need complex, high-accuracy model. I think it will be good to start with as simple as possible model. Try to apply it in real life. Check whether it is providing improvement/ROI for your business. Even simple ML model should be better than no model (random treatment). Simple models have beautiful advantage over complex one - they are human readable (yes, you can understand what is it doing!).
4. Use ML to make actions. You will feel the beautiful breeze of automation. The ML model is learning itself based on your data (you don't need to code it), then it is helping you to predict the future. Use it to make actions.
5. The commercial autoML solutions are pricey (50k-200k per year) so only big enterprises can afford it now. Beside that you still need a lot of resources to successfully deploy ML in the business. I think small and medium business will need to wait till the technology be more mature and therefore cheaper.

{% include newsletter.html %}
