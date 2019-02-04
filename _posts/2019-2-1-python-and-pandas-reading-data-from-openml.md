---
layout: post
title: Python and Pandas reading data from OpenML
---

The [Open Machine Learning](https://www.openml.org/) project is a movement to build online ecosystem for machine learning - it is free and open. It is huge repository of datasets that everyone can access. It is like [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php) but modern.

Let's try to read example dataset with Python and Pandas.

## Python and Pandas data reading from OpenML

As example, let's take _Adult_ data set ([link on openml.org](https://www.openml.org/d/1590)). It has id `1590`. You can download data manually from the web browser or read it directly in your python code.

Before going to code, you need to get OpenML API Key:

1. Register at openml and login
2. Go to your profile (top, right corner)
3. Search for API Authentication button - your API key will looks like similar to this: `adsd09asd0asd0asd0asd0a`

OK, API keys are ready. You will need to install `openml` python package (`pip install openml`). Let's code.

{% gist 89f2a311aef6add1a3bbc912f645202b %}

{% include newsletter.html %}
