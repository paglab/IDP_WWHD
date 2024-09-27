# IDP_WWHD

## Getting started.
### In order to establish the pipeline, please do the following steps:
#### 1) Please create virtual environment (e.g. anaconda).
#### 2) Install required packages via `pip install -r requirements.txt`.
#### 3-a) If you run the code via your local machine:
- Download the data via https://www.kaggle.com/datasets/cetinkayaevren/gwdh-2021 or https://zenodo.org/records/5092309 (original data, need some folder modifications. Available in `Pipeline.ipynb`).
- Add the dataset in `data(2021)` folder.
- Please run the notebook `Pipeline.ipynb`.
#### 3-b) If you run the code using Kaggle with their GPU:
- You can reach the GWHD 2021 dataset via: https://www.kaggle.com/datasets/cetinkayaevren/gwdh-2021
- Select the accelerator as `GPU T4 x2` in Kaggle.
- Upload the notebook called `kaggle-training-pipeline.ipynb` and run this notebook with given dataset.
#### 4-a) For evaluation of single models and calculation of Average Domain Accuracy (e.g. yolov8n):
- Please use the data you downloaded https://www.kaggle.com/datasets/cetinkayaevren/gwdh-2021 and put in `data(2021)` folder.
- Add your model to the `output_models` folder.
- Please run the `evaluate_GWHC2021.ipynb`.
#### 4-a) For evaluation of ensemble models and calculation of Average Domain Accuracy (**Our Main Evaluation**):
- Please use the data you downloaded https://www.kaggle.com/datasets/cetinkayaevren/gwdh-2021 and put in `data(2021)` folder.
- Put your ensemble models sent via email or cloud to the `ensemble_models` folder.
- Please run the `evaluate_ensemble_learning.ipynb` notebook.
#### OPTIONAL
- You can reach our single models' performances via comet.ml: https://www.comet.com/cetinkayaevren/wheat-head-detection/view/new/panels . However, it does not include ensemble learning performances.
- We tried another approaches to get the best Average Domain Accuracy. One of them was called subdomain approach. The main goal is to divide training dataset into 4 different dataset and group different domains (trainin data = 18 domains, 5-5-4-4 domains are splitted to each folder). Each 4 dataset is trained with their models (in total, 4 models) and ensemble learning evaluation is done. You can run `subdomain_approach_distribute_sample.ipynb` to split training data into 4 different folders, train via `Pipeline.ipynb` and evaluate the best models for 4 different dataset via `evaluate_ensemble_learning.ipynb`.
- Because it did not give any competitive result and not main approach, using this notebook is optional.