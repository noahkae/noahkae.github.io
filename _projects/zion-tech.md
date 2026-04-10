---
layout: project
title: 'Early Disease Prediction Tool'
caption: Hackathon-winning pre-screening tool
date: '10-03-2025'
image:
  path: /assets/img/projects/zion-tech.png
links:
  - title: Biohack 2025's Winning Submission
    url: https://github.com/zzaid17/biohack-2025
sitemap: false
accent_color: '#f39c12'
accent_image:
  background: '#3498db'
theme_color: '#3498db'
sitemap: false
featured: false
---
In early 2025, I joined a team of friends for [BioHack 2025](https://2025-biohackathon.devpost.com/), the first hackathon hosted by the [Bioinformatics Club](https://www.linkedin.com/company/ucalgary-bioinformatics-club) at the University of Calgary. Together, we built a disease prediction app in 24 hours driven by multiple machine learning models used to predict the likelihood of the user having certain diseases based on various input parameters. The app was built using Python and Flask and the front end was designed using HTML, CSS, and JavaScript, however my main area of contribution was in the machine learning backend. This was my first hackathon, and it ended up being an incredible learning experience capped off by our 1st-place finish and accompanying $400 prize.

In creating the models behind the prediction, 5 datasets were used; a [cancer](https://www.kaggle.com/datasets/rabieelkharoua/cancer-prediction-dataset) dataset, a [stroke](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) dataset, a [diabetes](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset) dataset, a [heart disease](https://www.kaggle.com/datasets/oktayrdeki/heart-disease) dataset, and a [liver disease](https://www.kaggle.com/datasets/rabieelkharoua/predict-liver-disease-1700-records-dataset) dataset. The use of 5 datasets was driven by the lack of a publicly available general disease dataset of sufficient quality, and as such multiple individual datasets and models were employed. I created a segment of code that iterated through many machine learning models such as random forests and logistic regression for each dataset, eventually selecting the most optimal via 10-fold cross validation. I also experimented with neural networks to perform the task, however they proved too volatile and prone to overtraining on the datasets. The models were then saved to .pkl files and integrated into the frontend. The complete submission is available on [github](https://github.com/zzaid17/biohack-2025).

![Submission](\assets\img\projects\GUI-working.gif)
A .gif showcasing the final application
{:.figcaption}
