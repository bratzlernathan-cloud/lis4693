###About our Dataset
##UFO Sightings around the world
#This data includes >80,000 recorded UFO "sightings" around the world, including the UFO shape, lat/long and state/country of where the sighting occurred, duration of the "event" and the data_time when it occurred.

#Data comes originally from NUFORC, was cleaned and uploaded to Github by Sigmond Axel, and some exploratory plots were created by Jonathan Bouchet a few years back.
#https://github.com/rfordatascience/tidytuesday/tree/main/data/2019/2019-06-25#ufo_sightingscsv

###Contents 

##The copendium contains the data, code, and notebook associated with the analysis. It is organized as follows:

#The copy_of_final_project_draft.ipynb file contains the complete Jupyter notebook for all analysis steps, including preprocessing, topic modeling, network analysis, and classification. 

#The network.png file is a generated output-- a word co-occurrence network graph produced from the top 50 most frequent terms across all UFO sighting reports. 

##Notebook Structure
#The notebook is divided into the following sections: 
##1. Data Loading
#Loads the UFO sightings dataset directly from the TidyTuesday GitHub repository using pandas. The dataset contains over 80,000 eyewitness reports of UFO sightings.

##2. Text Preprocessing
#Cleans and normalizes raw description text using nltk. Steps include lowercasing, punctuation removal, stopword filtering (with a custom domain-specific stopword list), and lemmatization via WordNetLemmatizer.

##3. Topic Modeling (LDA)
#Applies Latent Dirichlet Allocation (LDA) using scikit-learn to discover 8 latent topics across the corpus. A CountVectorizer document-term matrix is constructed with max_df=0.95 and min_df=10 thresholds before fitting the model.

##4. Word Network Analysis
#Builds a word co-occurrence graph using networkx from the top 50 most frequent lemmatized terms. Edges are weighted by co-occurrence frequency within individual reports. The resulting network is visualized with matplotlib and saved as network.png.

##5. Word Frequency Visualization
#Generates an interactive horizontal bar chart of the 15 most common words using altair, showing word frequency across the full cleaned corpus.

##6. UFO Shape Classification
#Trains a Logistic Regression classifier using a TF-IDF pipeline (CountVectorizer + TfidfTransformer) to predict the reported UFO shape from the description text. Shapes with fewer than 50 reports and ambiguous labels (unknown, other) are excluded. Model performance is evaluated with accuracy, a full classification report, and a confusion matrix heatmap (via seaborn

