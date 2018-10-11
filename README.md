# CCTV mood

> Work in progress, still buggy

Detect mood in video. This is a reconstruction of cool CCTV example that I saw at a Spark + AI [talk](https://databricks.com/session/analyzing-performance-bottlenecks-in-data-science-the-case-for-distributed-models-using-apache-spark) by Thunder Shiviah. You can also have a look at my [minutes](navigating-ml-jungle.md) of the talk.

The example is in the notebook [proto-vgg16-nn.ipynb](proto-vgg16-nn.ipynb) (most stable). There is also a version that uses LSTM to classify sequences of video frames. I actually created that one first, but found that it was overkill for the example. 

## Outline

Training:

1. Record a set of "relaxed" and "excited" videos on Mac Book Pro web cam.
1. Extract features using pre-trained feature extractor on individual frames.
1. Train a model that can tell the difference between relaxed and excited, using Logististic Regression or LSTM. Probably the latter.

Inference:

1. Continuously capture video from Mac Book Pro web cam.
1. Print either "safe" or "danger"

Project dependencies:

```
Python 3.6
pip install keras
pip install tensorflow
pip install numpy
pip install Pillow
pip install opencv-python
```

## Articles this tutorial is based

https://www.learnopencv.com/read-write-and-display-a-video-using-opencv-cpp-python/
https://medium.com/@franky07724_57962/using-keras-pre-trained-models-for-feature-extraction-in-image-clustering-a142c6cdf5b1

(didn't work) https://becominghuman.ai/extract-a-feature-vector-for-any-image-with-pytorch-9717561d1d4c
