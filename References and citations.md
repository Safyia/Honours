###References

*Sentiment Analysis and Opinion Mining Synthesis Lectures on Human Language Technologies*, Vol. 5, No. 1. (23 May 2012), pp. 1-167, [doi:10.2200/s00416ed1v01y201204hlt016](doi:10.2200/s00416ed1v01y201204hlt016) by Bing Liu

 *Twitter as a corpus for sentiment analysis and opinion mining*.
In Proceedings of LREC (2010), by Alexander Pak and Patrick Paroubek

*Thumbs Up or Thumbs Down?: Semantic Orientation Applied to Unsupervised Classification of Reviews* In Proceedings of the 40th Annual Meeting on Association for Computational Linguistics (2002), pp. 417-424, [doi:10.3115/1073083.1073153](doi:10.3115/1073083.1073153) by Peter D. Turney

*Semantic sentiment analysis of twitter* In Proceedings of the Semantic Web–ISWC (2012), pp. 508-524, by
Saif, Hassan, Yulan He, and Harith Alani

*Twitter sentiment classification using distant supervision*
In-text: (Go and Bhayani et al., 2009, pp. 1-12)
Bibliography: Go, A., Bhayani, R. and Huang, L. 2009. Twitter sentiment classification using distant supervision. CS224N Project Report, Stanford. [report] pp. 1-12.


###Paper summary

The report describes sentiment classification of twitter data and the preprocessing steps that are needed to achieve high accuracy. Instead of using hand-labelled training data, distant supervision is applied, where training data consist of tweets with emoticons. Only positive and negative tweets are used. As neutral tweets are considered those that could appear as a newspaper headline or sentences in Wikipedia. Three machine learning classifiers are used in this approach - Naive Bayes, Maximum Entropy and Support Vector Machines. 

Preprocessing of data includes replacing words starting with a @ symbol by an equivalence class token USERNAME and urls by a a token URL. Letters that occur in a word more then two times in a row are replaced with two occurrences. After these changes the feature sets size is reduced to approximately 46% of its original size.
The polarity of a tweet is calculated from the number of negative and positive keyword appearances. If the numbers in a tweet are same, positive polarity is returned.

For training data a scraper is used to query the Twitter API periodically.  The scraper send two queries, one for :) and one for :(, with twitter API mapping other emoticons. Emoticons are considered to be noisy labels that have a negative impact on the accuracy(especially MaxEnt and SVM), therefore these are stripped  from the training data to enable the classifier to learn from ngrams in the tweet. Tweets containing positive as well as negative emoticons, and retweets are removed (1 600 000 tweets).  
For test data a manually collected and marked set of tweets is used. (359 tweets).

The usage of unigrams, bigrams, unigrams and bigrams, and parts of speech as features is explored. The results of 81.3%, 80.5%, and 82.2% were achieved for Naive Bayes, Max Entropy and SVM respectively for unigrams. In case of bigrams the accuracy drops for SMV and MaxEntropy algorithms. When using both unigrams and bigram the accuracy improved for Max Entropy and Naive Bayes by approximately 1.5%, but dropped for SVM (0.6%) The part of speech tags were fount not to be useful.



