# How To Use The Notebooks As Intended
## (Inside The A100_Ensemble Directory)

### EfficientNet.ipynb & SWINbase.ipynb
Run each cell sequentially. In the configuration cell, you can toggle the USE_VALIDATION flag to true if you would like to train with an 80/20 train/val split. Set to false if you would like to train on 100% of the training set(we only used this to generate our final submission).

We have cells to generate csv submission with or without TTA. This is useful for comparing accuracy with vs without TTA.

### ensemble.ipynb
This notebook first checks if the model weights are present, then runs TTA inference on both, collecting their softmax probabilities on each prediction. It then ensembles the predictions of both models to generate a csv with ensembled predictions.

### Important Notes
We ran our models on a VM using runpod.io. Our VM had an Nvidia A100SXM GPU with a 32 core CPU. This is why we have large image resolutions and batchsizes, as well as flags on our dataloaders to increase the number of workers and pre-fetch more images.

### Link To Report
https://docs.google.com/document/d/1CxocJlXFPNqODtLj7CC_aOccgh1WrJvsbWQzKF92XPE/edit?usp=sharing
