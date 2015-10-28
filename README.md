# SearchEngine
Its a free query search engine written in java.
In order to add documents use addDocument class and to search the documents use SearchRunner Class.
In order to rank documents based on the given Query we have used TF-IDF and Okapi probabilistic model.
We have also implemented F measure to judge the correctness of results returned.

###This project aims to build a News indexer with the following goals:
•	Parse simple news articles with minimal markup
•	Index a decent sized subset of the given news corpus.
•	Create multiple indexes on the news articles as well as metadata.
•	Provide an index introspection mechanism that can later be built upon to support queries.
•	Implement a query parser that can parse free text into structured query terms
•	Implement a querying mechanism that can ingest query terms and find matching documents
•	Implement two popular scoring mechanisms to rank retrieved documents
•	Implement one or more methods to improve search engine relevancy scores.

##Components:-

####Parser
This component is responsible for converting a given text file into a Document representation. A Document is nothing but a collection of fields. Each field can have its own indexing strategy that would be applied by the IndexWriter.

####Tokenization
This stage is responsible for transforming the given Document class instances into Tokens (technically TokenStream instances but read on).

####Analyzer
This is an interface that defines operations over TokenStream objects. Multiple Analyzer instances can be chained to allow successive operations on a given TokenStream. There are two levels of usage – either as a single Analyzer as a TokenFilter instance or as a chained Analyzer applicable for a given FieldName.

####IndexWriter
Once a given file has been converted into a Document, the IndexWriter is responsible for writing the fields to the corresponding indexes and dictionaries. 

####Query Parser
This component is responsible for converting a given raw string query into a Query representation.  A Query is nothing but an ordered collection of Clauses that are connected by Boolean operators.

####Index Searcher
As the name suggests, this component is responsible for consuming the given Query object and use it to search through the given Index to retrieve documents. 

####Scorer
The set of documents retrieved by the Index Searcher need not be in any order. The Scorer is responsible for ranking the results based on their relevance to the query.
