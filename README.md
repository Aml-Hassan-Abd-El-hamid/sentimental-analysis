# sentimental-analysis
This repo started as a part of the technical assessment for Cyshield, they sent 3 tasks with 14 days time limit, The rest of the tasks will be published as GH repos too for anyone who's interested in looking into them :)

That was the task body:

```
▪ Write a pipeline coding to solve the main problem in NLP that relay to the Homonyms in the sentence and how to overcome these problem we faced 
in sentimental analysis .and the contextual problems such as . 
✓ U can use Deep Learning Methods and show the diff and which one the best.(optional)
▪ Here we have two sentence 
{“Sentence” : “I hate the selfishness in you ”,”label": negative}
{“Sentence": "I hate any one who can hurt you ”,”label”: positive} .
▪ Write the report and mentioned how we can handle this problem for customer.
▪ Feel free to use any technique can help to solve this problem .
✓ U can use Deep Learning Methods and show the diff and which one the best.(optional)
```

The whole issue with this problem is the fact that each word has a single representation that doesn't pay **attention** to its neighbourhood model, so the solution can be to use a model that produces embeddings aware of the word's context, the **BERT** family can be a very good solution for that problem.  

## Dataset
There were multiple types of datasets that I found during my hunt for a dataset and I like to mention some of them right here for future use
Dataset Link | Desc | size | lang
--- | --- | --- | ---
https://www.kaggle.com/datasets/mksaad/arabic-sentiment-twitter-corpus | That's an automatically created dataset, it's assumed by its creators that any tweet with positive emoticons, like :), were positive, and tweets with negative emoticons, like :(, were negative. The dataset contains 2 emotions, negative, and positive<br> it's a balanced dataset with the training and the testing already separated <br> I'm not a big fan of that dataset given the fact that it's not checked by Humen | 56K samples | ara (mixed dialects)
https://www.kaggle.com/datasets/attiabendjedou/algerian-arabic-sentiment-analysis-dataset/data | very interesting dataset given its in a dialect that I've never worked with before<br> It contains 979 negative samples and 521 positive samples<br>There are some weirdly labelled sample for example, this "بوتسريقة أس 2" is labelled negative <br>there's no info about the source in the dataset card | 1,500 samples | ara (Algerian)
https://www.kaggle.com/datasets/hamzazaki/arabic-text-paired-with-sentiment-labels | That dataset is very neat, it's simple Arabic sentences with its emotion, the only issue is that it's very small | 175 samples | ara (MSA)
https://www.kaggle.com/datasets/abedkhooli/arabic-100k-reviews | The dataset is promising but a lot of samples seem to have a mislabelled emotion, eg: those samples "وهذا ما سيحدث معنا", "عمان . كل شي. لا يوجد", are labelled positive | 100K samples | ara (MSA with some dialects)
https://homepages.inf.ed.ac.uk/wmagdy/resources.htm | The dataset is a set of 21K Arabic tweets labelled for 4 classes of sentiment and 6 classes of speech-act, it contains 4,400 positive samples	7,384 negative samples | 19,897	| ara (mixed dialects)
 
I decided to go with the [ArSAS](https://homepages.inf.ed.ac.uk/wmagdy/resources.htm) dataset given that it's humanely evaluated, that dataset contains the following features: `#Tweet_ID`,	`Tweet_text`,	`Topic`,	`Sentiment_label`,	`Sentiment_label_confidence`,	`Speech_act_label` and	`Speech_act_label_confidence`.<br> 
We focus on 2 features from that dataset which are: `Tweet_text`, `Sentiment_label` and `Sentiment_label_confidence`, The dataset's `Sentiment_label` is interesting cause it doesn't only have positive and negative but also: Neutral and Mixed.

I excluded any sample that has a `Sentiment_label_confidence` less than 100%, and that filtered the dataset so it became only 10,847 samples, after that filtration, the samples labelled `mixed` were very rare, so I dropped them and focused on the rest of the classes, so the new no.of samples became **10,712**.
<img src="https://github.com/user-attachments/assets/f946d1d7-dd76-401c-bb62-b5d64e28ef84" width="400" height="400" >



## Modelling
 
## Useful references:
- https://medium.com/swlh/differences-between-word2vec-and-bert-c08a3326b5d1
