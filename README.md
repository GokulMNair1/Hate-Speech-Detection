# Hate-Speech-Detection

Hate Speech Predicational Analysis is the process of computationally identifying and categorizing opinions expressed in a piece of text, especially in order to determine whether the writer's attitude towards a particular topic, product, etc. is positive, negative, or neutral. Hate Speech Prediction analysis is becoming a popular area of research and social media analysis, especially around user reviews and tweets. It is a special case of text mining generally focused on identifying opinion polarity, and while it’s often not very accurate, it can still be useful. For simplicity (and because the training data is easily accessible) we will be focusing on 3 possible Hate Speech Prediction classifications: positive, negative and neutral.

## DESIGN GOALS:
To implement an algorithm for automatic classification of tweets into Positive, Negative or Neutral with highest accuracy possible. The tweets cab be gathered to summarize the overall Hate Speech Prediction on a particular topic.
![image](https://user-images.githubusercontent.com/110875197/183559866-ed707c8b-4562-444f-a4f2-c38b51abbdbe.png)

### IMPLEMENTATION:

![image](https://user-images.githubusercontent.com/110875197/183560122-ac7c4618-cf14-4cf3-9545-2c6217448635.png)

A) PRE-PROCESSING:

1.	Convert to lowercase

2.	Replace @user with at user.

3.	Replace #Tag with Tag.

4.	Replace http://www.url.com with URL.

5.	Remove special characters that doesn’t affect Hate Speech Prediction.

Tweet before preprocessing is as follows:
Tweet = “@sooraj \\ I can't afford flight tickets of http://www.jetways.com but I can buy train ticket. #sad”

Tweet after preprocessing is as follows:

Tweet =“at user i can't afford flight tickets of URL but i can buy train ticket. sad”



B) CREATING FEATURE VECTOR:

1.	Tokenization

2.	Replace two or more with two occurrences

3.	Remove the word that doesn’t start with alphabet

4.	Remove all stop word which doesn’t have any Hate Speech Prediction
Tweet after preprocessing before creating feature vector is as follows:

Tweet =“at user i can't afford flight tickets of URL but i can buy train ticket. sad

Tweet after creating feature vector is as follows   FeatureVector = “ can't, afford, but, can, buy., sad ”                   

C) CREATE NEGATED FEATURE VECTOR:

1.	Attach “not_” to words which have negation impact.

2.	Remove negation words.

3.	Remove the remaining punctuation.

Tweet after creating feature vector is as follows:

FeatureVector = “ Not_afford, can, buy, sad ” Hate Speech Prediction = “positive”

D) CREATE FEATURE LIST:

FeatureList = FeatureList + FeatureVector

FeatureList = FeatureList + [Not_afford, can, buy, sad]

E) APPENDING HATE SPEECH PREDICTION AND FEATURE VECTOR:

Tweets = Tweets + [“positive, Not_afford, can, buy, sad”]

F) REPEAT STEP A TO E:

Step from A till E is repeated for each tweet in training set to get complete list of Processed Tweets and Feature List.


# Hate Speech
![hate_speech](https://user-images.githubusercontent.com/110875197/183563563-f9a9e00f-a960-4c4b-87ce-eeeee0b616ab.png)

# Offensive Language 
![offens_lang](https://user-images.githubusercontent.com/110875197/183563619-d5f66c9c-d261-490d-9789-c398b63e177d.png)

# Neither
![neither](https://user-images.githubusercontent.com/110875197/183563650-ef95ebcb-79e7-40c3-b321-916b5347444c.png)
