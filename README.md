# LuceneSearchEngine #

This repository contains the code for the implementation of an information retrieval system using Lucene Core, a Java library providing powerful indexing and search features. The system is designed to index the documents in the Cranfield collection and evaluate the results using trec eval, a standard tool used by the TREC community for evaluating retrieved results.

## Implementation ##

The Cranfield dataset, which includes 225 queries and 1400 documents, is processed using several file handling techniques, including indexing and querying. Maven framework is used to manage dependencies and create an executable jar file to run the program.

## Choice of Analyzer and Score (Similarity) ##

The Lucene English Analyzer is used as the best choice since it is a grammar-based analyzer that includes a stop word filter, stemming filter, lower case filter, standard filter, English processive filter with standard tokenizer, leading to a good performance. The score or similarity used is bm25 since it is a probabilistic model rather than vector space model, which suits well with documents in the Cranfield dataset, as it includes articles length pieces of text.

## Performance of Search Engine ##

The search engine's performance is evaluated using relevance judgments provided in the Cranfield dataset. Using trec eval, several parameters are populated. Some of the important parameters are:

 - runid=English: Signifies the used Lucene analyzer is English
 - num_q=225: Signifies the number of queries used
 - map=0.4276: Signifies the Mean Average Precision
 - iprec_at_recall_(0.00 to 1.0): Signifies the precision averages for each recall, which has been plotted on the graph for better understanding. From the graph, we can see that the highest precision average is 0.8232 when recall is 0.00 and the lowest precision average is 0.1367 when recall is 1.00.
 - p_(5 to 1000): Signifies the precision after fetching n number of documents retrieved (where n varies from 5 to 1000).
