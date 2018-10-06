# CCTV suspicious behaviour

Reconstruction of cool CCTV example that I saw at a Spark + AI [talk](https://databricks.com/session/analyzing-performance-bottlenecks-in-data-science-the-case-for-distributed-models-using-apache-spark) by Thunder Shiviah. You can also have a look at my [minutes](navigating-ml-jungle.md) of the talk.

Dependencies:

```
pip install torch
pip install torchvision
pip install numpy
pip install Pillow
pip install opencv-python
```

## Outline

Training:
1. Record a set of normal and suspicious videos on Mac Book Pro web cam.
1. Extract features using pre-trained feature extractor on individual frames.
1. Manually label normal and suspicious frames, using pre-trained feature extractor.
1. Train model (trying Logististic Regression and LSTM).

Inference:
1. Capture video from Mac Book Pro web cam.
1. Extract features with pre-trained feature extractor and run through trained model.
1. Play an alarm sound (or display text) if suspicious behaviour is detected

## Articles this tutorial is based

https://www.learnopencv.com/read-write-and-display-a-video-using-opencv-cpp-python/
https://medium.com/@franky07724_57962/using-keras-pre-trained-models-for-feature-extraction-in-image-clustering-a142c6cdf5b1

(didn't work) https://becominghuman.ai/extract-a-feature-vector-for-any-image-with-pytorch-9717561d1d4c
