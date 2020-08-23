# Parts-Of-Speech-tagging-NLP
Parts of Speech Tagging using HMM-Viterbi approach and modifications in the approach for better tagging

# Problem
Hidden Markov Model & Viterbi approach is an approach used for POS tagging in NLP. This is an heuristic approach as this identifies the probabilities of a given word belonging to a particular POS tag given only the last preceding word and not all of the preceding words. Hence it gives a good benefit in terms of execution time. As we dont need to check for the probabilities of all the preceding words.
It uses the concept of *Emission Probability* and *Transition Probabiity*, together it helps to identify the POS having highest probability given the preceding word/POS tag.

We can notice that Plain Viterbi algorithm works efficiently, however there is a scope for improvement, as the alogorithm is not able to perform well for words which were not there in the training data. For the words which were not present in the training data it just assigns first POS tag, which is incorrect. This scenario is very common in real world as there can be multiple scenarios where we encounter new words which were not present in the training data. Hence we need to put some backoff algorithm for such missing words scenario.

# Modified Solutions
Here we have used a modification over the Plain HMM-Viterbi algorithm. 
Modification 1 : We tried to put an Rule Based Tagger for the scenarios where the words itself is not present in the training data.
Modification 2 : For the second scenario, we have tried Unigram or Laxicon Tagger(backed off by Rule Based Tagger) for the scenario of missing word in train data. We had to use the back-off as Laxicon will also fail if the word is not present in the training data.
