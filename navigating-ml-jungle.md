# Navigating the ML Pipeline Jungle with MLflow: Notes from the Field

https://databricks.com/session/analyzing-performance-bottlenecks-in-data-science-the-case-for-distributed-models-using-apache-spark

Speaker: Thunder Shiviah
Session hashtag: #SAISDS11
Topics: MLFlow, model factory

> MLFlow solves the hard problem in AI, i.e. plumbing

## Three no-brainers for Spark and Pandas combination

Data scientists like Pandas, but memory footprint is horrible.

- use Apache Arrow (columnar format) to improve Pandas memory footprint, with `to_pandas()`.
- Use @pandas_udf
- Forgot what the last one was...

Calling your model in Spark UDF.

## CCTV example

Can't find exact Databricks code from presentation, but below I've made an attempt to gather the threads.

! guy said video will be made available on Spark Summit website. This was a good talk by former McKinsey employee. Why are those guys and girls always so sharp?

Overview of problem solved
- https://databricks.com/blog/2018/09/13/identify-suspicious-behavior-in-video-with-databricks-runtime-for-machine-learning.html
- https://dzone.com/articles/video-analysis-to-detect-suspicious-activity-based
Feature extraction
- (Keras) https://medium.com/@franky07724_57962/using-keras-pre-trained-models-for-feature-extraction-in-image-clustering-a142c6cdf5b1
- (PyTorch) https://becominghuman.ai/extract-a-feature-vector-for-any-image-with-pytorch-9717561d1d4c
Pipeline from talk (sketch)
- sparkdl
- cv2 extract frames from video
-- https://stackoverflow.com/questions/33311153/python-extracting-and-saving-video-frames
- USing pretrained DeepImageFeatureExtractor (Keras?)
- apply logistic regression (or how about lstm?) to output

Task: recreate suspicious behaviour in cctv video example

## Questions

- Re. MLFlow and decoupling feature vector from model, something something
-- Andrey Karparthy at 2018 summer school: need for software 2.0 that supports data science
- At what point should Data Scientists switch from single node to distributed
-- Non-zero cost: distributed loses cool single-node libraries, but mitigate somewhat with @pandas_udf. But maybe start with SparkML
