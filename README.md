# Lyric-based Playlist Continuation with Transformers
### SP '23 CSE 256 Project

Our aim was to investigate the effectiveness of incorporating lyrics into music recommendation systems. Specifically, we proposed using a transformer architecture for mood classification based on lyrics, whose results are used for subsequent music recommendation. We were able to accomplish all the tasks we set out to to in the proposal and were also able to obtain good results, better than the cited papers in some aspects.

The following is a description of all the files in this repository.
* [The project proposal document](cse256_project_proposal_Personal.pdf)
* Data Collection and Preprocessing for Mood Classification
  * [data/fetch_lyrics.ipynb](data/fetch_lyrics.ipynb) contains code to fetch song lyrics for all the tracks listed in MoodyLYrics Dataset using the Genius API.
  * [data/data_split.ipynb](data/data_split.ipynb) splits the MoodyLyrics dataset into train, validation, and test sets to train and evaluate our models.
* Mood Classification
  * [models/baseline-nb-72.ipynb](models/baseline-nb-72.ipynb) fits and evaluates our baseline - Naive Bayes, for mood classification.
  * [models/bert-base-64-lr_sch-3eps-0.77.ipynb](models/bert-base-64-lr_sch-3eps-0.77.ipynb) is our initial training and evaluation (on the validation set) of BERT for mood classification.
  * [models/bert-base-256-5eps-0.94.ipynb](models/bert-base-256-5eps-0.94.ipynb) contains the verison of BERT for mood classification that gave the best performance.
  * [models/xlnet-base-256-5eps-0.91.ipynb](models/xlnet-base-256-5eps-0.91.ipynb) we also tried fitting and evaluating the XLNet Architecture for mood classification.
  * [models/final_bert_model_with_test_evaluation.ipynb](models/final_bert_model_with_test_evaluation.ipynb) contains the final best-performing model for mood classification (BERT) evaluated on the test set.
* Data Collection and Preprocessing for Recommendation
  * [data/mpd-fetch-lyrics.ipynb](data/mpd-fetch-lyrics.ipynb) fetches lyrics for a subset of tracks in Spotify-Million-Playlist Dataset.
  * [data/interactions_data_split.ipynb](data/interactions_data_split.ipynb) splits the recommendation playlist-track data into train, validation, and test sets.
* Recommendation
  * [recommendation/baseline_collaborative_filtering.ipynb](recommendation/baseline_collaborative_filtering.ipynb) contains code for our baseline - collaborative filtering approach for recommendation.
  * [recommendation/lightfm.ipynb](recommendation/lightfm.ipynb) builds the LightFM candidate track selection model.
  * [recommendation/xgboost_no-mood-features.ipynb](recommendation/xgboost_no-mood-features.ipynb) trains our final stage recommendation model with XGBoost without incorporating any mood-based features.
  * [recommendation/xgboost_with-mood-features.ipynb](recommendation/xgboost_with-mood-features.ipynb) trains XGBoost for recommendation of candidate tracks by including mood-based features.
* [Final Project Report](cs256_project_finalreport_personal.pdf)
