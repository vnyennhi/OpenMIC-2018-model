# OpenMIC-2018-model

0. First, make sure you [download the dataset](https://zenodo.org/record/1432913#.W6dPeJNKjOR)! and extract to the folder 'data'.

1. To set up the environment, you can follow the instructions to install `pipenv` [here](https://pypi.org/project/pipenv/), then run the following to install dependencies:
```
$ pipenv install
```
To activate this project's virtualenv, run the following:
```
$ pipenv shell
```
Then you can open Jupyter Lab by running:
```
$ pipenv run jupyter lab
```

2. To download VGG model ckpt (only needed if you want to run the last section on the notebook regarding applying model), run the download script (requires `wget`):
```
$ ./download-deps.sh
```

3. Running models: Notebooks are numbered but not required to run in sequential order.
- The first notebook `0-modeling-baseline-sklearn-random-forest.ipynb` is adapted from this [example](https://github.com/cosmir/openmic-2018/tree/master).
- The second notebook `1-modeling-xgb.ipynb` is similar, using XgBoost to achieve slightly higher recal and F1. I did not have time to do further parameter tuning to improve the results with XgBoost.
- The third notebook `2-modeling-deep-learning-with-vgg.ipynb` is using a simple neural networks model. I run out of time before I can find an architecture that works for this case.

### Current results:
Metrics | Precision | Recall | F1
--- | --- | --- | ---
Model 0 | 0.8239 | 0.7752 | 0.7834
Model 1 | 0.8055 | 0.7840 | 0.7913
Model 2 | 0.7760 | 0.7535 | 0.7261

### TODO: 
If there were more time, I would love to explore extracting sound features as well as testing more feature engineering to improve the model performance. I copy here the `utils.py` file from [my other project](https://github.com/vnyennhi/AICovidVN-115M/tree/main) that I intend to use `librosa` to extract sound data and combine with other features.
