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

The whole issue with this problem is the fact that each word have a single representation that doesn't pay **attention** to its neighbourhood model, so the solution is to use a model that produce embeddings aware of the world's context, the **BERT** family can be the perfect solution for that problem.  

Useful references:
- https://medium.com/swlh/differences-between-word2vec-and-bert-c08a3326b5d1
