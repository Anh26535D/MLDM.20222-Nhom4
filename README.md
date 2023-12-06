# Predict Student Performance from Game Play
[Competition link](https://www.kaggle.com/competitions/predict-student-performance-from-game-play/overview)

## Description

Learning through games is an educational method that allows students to interact with educational content within the framework of a game, making the content interesting and dynamic. Although game-based learning is increasingly used in educational environments, there are still limited open datasets available for applying data science and learning analysis principles to improve game-based learning. Most game-based learning platforms do not fully harness the potential of knowledge tracing to support each student. Knowledge tracing methods have been developed and researched in the context of online learning environments and intelligent tutoring systems, but there has been little focus on knowledge tracing in educational games.

Therefore, Field Day Lab, a publicly funded research laboratory at the Wisconsin Center for Education Research, along with The Learning Agency Lab, organizes this competition on Kaggle with the goal of using machine learning models to predict students' performance in games. This aims to help developers improve their game-based learning platforms.

The game named Jo Wilder is a hidden educational game containing 18 questions within its gameplay. **Participants' task in the competition is to predict whether a player can correctly answer the hidden questions in the game based on the recorded information during the player's gameplay.**


## Prerequisites
 - Python 3.9 or later.

## Installation
1. **Clone project**
  ```
    git clone 
  ```
2. **Install python libraries**
  ```
    pip install -r requirements.txt
  ```

## File Structure
  - data_preparation.ipynb: File preparing the dataset from the original training set.
  - lgbm_BO_hyperparams_tuning.ipynb: File running Bayesian Optimization for the prepared dataset.
  - lgbm_boruta_feature_selection.ipynb: File running Boruta Feature Selection for the prepared dataset.
  - lgbm_train_and_inference.ipynb: File submitting results to Kaggle (after uploading the necessary files to Kaggle).
  - lgbm_validation.ipynb: File running LightGBM to remove features.
  - pre_eda.ipynb: File exploring the original data.

## Usage
* The order of running the files (note that the order of CSV files is not guaranteed due to the randomness of BO and BORUTA; these files are only used for the final submission to the competition - except for hyperparams_tuning.csv with the reason explained below):
  - `data_preparation.ipynb` will generate 3 training pickle files: `train_0_4.pkl`, `train_13_22.pkl`, `train_5_12.pkl`.
  - `lgbm_validation.ipynb` will generate 1 `FEATURES_Q.csv` file, which contains the features used for the next step.
  - `lgbm_boruta_feature_selection.ipynb` takes features from `FEATURES_Q.csv`, then runs to get the second round of filtered features (note that the code currently does not save automatically, only prints out, so manual copying is temporarily required) to the `BORUTA_FEATURES.csv` file.
  - `lgbm_BO_hyperparams_tuning.ipynb` takes the `FEATURES_Q.csv` file to generate parameters (note that the code currently does not save in a standardized format, so manual adjustment of the format of the generated file is needed) in the `hyperparams_tuning.csv` file. After that, it is necessary to use the customized parameters from the previous step (already available in the files) to manually fine-tune the parameters again for each question (18 questions). Note that BO does not guarantee the same parameter set for different runs.
  - `lgbm_train_and_inference.ipynb`. This file needs to be used on Kaggle. Go to the home page of the competition using the link above, select a new notebook, and then upload this file. Additionally, upload the training pickle files from step 1, the `BORUTA_FEATURES.csv` file from step 3, and the `hyperparams_tuning.csv` file from step 4 (optional and may not be used due to time constraints; the team did not use this parameter set for successful submissions but only used features from BORUTA).


## Contributors
* Đàm Việt Anh - 20204627 - anh.dv204627@sis.hust.edu.vn
* Vũ Việt Anh - 20200053 - anh.vv200053@sis.hust.edu.vn
* Phạm Quang Minh - 20204588 - minh.pq204588@sis.hust.edu.vn
* Nguyễn Trung Hiếu - 20204551 - hieu.nt204551@sis.hust.edu.vn
* Trịnh Quang Quân - 20200511 - quan.tq20200511@sis.hust.edu.vn
