# Ecommerce Recommender System
Recommender Systems (or RecSys as they are widely known) can be found in many modern day applications ranging from e-commerce websites like Amazon to music platforms like Spotify. Through this work, we fine-tuned a BERT4Rec model that can leverage user behavioral data to make similar or relevant product recommendations for the user to consider. We used a publicly available dataset to train the model and then evaluated it on popular evaluation metrics used to quantify recommender system performance. On the test dataset, our fine-tuned BERT4Rec model achieved Recall@10 of around 60% and an NDCG@10 of 45%.

The docs folder contains the project proposal, presentation and final report.

# About BERT4Rec
BERT4Rec is a Sequential Recommendation system built on the BERT architecture. It leverages the multi-headed self-attention introduced with BERT to make recommendations based on historical sequence representations.

<a href="https://arxiv.org/abs/1904.06690">BERT4Rec: Sequential Recommendation with Bidirectional Encoder Representations from Transformer</a>

# Getting the Data
The raw dataset can be found at https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store/data. Go to the link and download the 2019-Oct.csv file into the data folder in the repository. The file is too large to be uploaded to Git.

# Analyzing columns in raw data
Run the data_analysis.ipynb notebook to look at the raw data distributions. The insights from this stage were used in the data cleaning process. The file is too large to be uploaded to Git.
 
# Cleaning the data
Run the data_cleaning.ipynb notebook. This code will clean the dataset and generate a csv file called cleaned_data.csv in the data folder.

# Creating the dataset object
We use the RecBole library for interacting with the BERT4Rec model. In order to do so, we need to create a custom dataset object that is specific to RecBole which can be done using the creating_dataset.ipynb notebook. This file separates the dataset into three atomic files: user, item and inter which contain data about the user, product and their interaction respectively. These atomic files will then be used to create the dataset object which will be fed to the model.

# Training the model
Run the bert4rec.ipynb notebook. The code uses the RecBole library to train the BERT4Rec model. You will see that the model uses a ecommerce.yaml file - this file acts as the configuration file for the model. It contains the training params as well as some data preparation variables. It tells the model what to do with the data.
