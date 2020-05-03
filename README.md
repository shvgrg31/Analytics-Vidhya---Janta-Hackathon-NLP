# Analytics-Vidhya---Janta-Hackathon-NLP
Predicting if a user recommends a game or not from review and game details.

We have a training dataset which contains <b> title of the game, user_review, if user suggested the game, review id </b> and another dataset containing the information about each of the 64 games including <b> year of launch, title, overview and genre tags of the game. </b> <br> 
Initital analysis reveals the <i> games present in the training data are different from the games present in the test dataset</i>. The datasets were fairly distributed between positive and negative examples. Only "year" column had missing values and can be replaced by the value of last game released by the developer or publisher. 

Two models were built:
<ol> 
  <li> Model based on non-review data comprising of the games developer, publisher, overview of the games (using tf-idf). The model was able to achieve a f1-score of 0.73 on its own. </li>
  <li> Review data were first pre-processed to remove urls, numbers, stop-words, punctuations and curse-words. Heart emoji were replaced by <heart-emoji>, space was added before "I" and after a ".", non-ascii characters were removed and only english characters were considered. After pre-processing the empty processed reviews (containing urls, non-english reviews) were replaced by word "recommended" and "not recommended" depending on the target variable. Then n-grams (n=4) were created and tf-idf were created. Standard classification algorithms were tried followed by single and bi-directional LSTM methods. I was able to achieve a f1-score of 0.86. Also I tried experimenting with Textblob librarys's sentiment analysis and their polarity to obtain general emotion of the review. This can be used as a feature during classificaiton. </li>
</ol>

Things that can be tried in future:
<ol>
  <li> Word embeddings of review to capture syntactic information </li>.
  <li> Transfer learning using Pre-trained models </li>    
