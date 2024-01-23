# Information Retrieval on Scientific Paper Abstracts

## Project Description

This project revolves around the retrieval of information from a dataset comprising 1400 HTML files, each containing the title, author name, and abstract of scientific papers. The primary objectives include data preprocessing, the construction of unigram and bigram inverted indices, positional indexing, TF-IDF matrix generation, and support for boolean and phrase queries.

## Dataset Description

The dataset consists of 1400 HTML files, each containing the title, author name, and abstract of a scientific paper. The data was provided by Cranfield University.

## Data Preprocessing

For each of the 1400 files in the dataset, we performed the following steps:

1. **Relevant Text Extraction:** We extracted the contents between the `<TITLE>...</TITLE>` and `<TEXT>...</TEXT>` tags, concatenated the two strings using a blank space, and discarded the rest of the text. The resulting string was saved back to the same file.

2. **Preprocessing Steps:**
   - **Lowercasing:** We converted all text to lowercase.
   - **Tokenization:** We tokenized the text using the NLTK library's `word_tokenize()` method.
   - **Stopword Removal:** We removed common stopwords using NLTK's stopword corpus.
   - **Punctuation Removal:** We removed punctuation marks from the text.

Before and after performing each of these operations, we printed the contents of sample files to illustrate the changes.

### TF-IDF Matrix Generation

We generated TF-IDF matrices for the documents in the dataset. The following TF weighting schemes were employed:

1. **Binary Weighting:** Binary representation of term frequency.
2. **Count Weighting:** Term frequency counts.
3. **Frequency Weighting:** Frequency normalized by document length.
4. **Log Normalized TF:** Logarithmically normalized term frequency.
5. **Double Normalized TF:** Double normalization of term frequency.

For each term, we maintained dictionaries containing the corresponding TF values for each document and calculated document frequencies (DF). These TF-IDF matrices provide a basis for various information retrieval tasks.

### Jaccard Index

We also calculated the Jaccard Index for documents based on their word sets. This index measures the similarity between documents and can be useful for document retrieval and clustering.

For queries, we preprocessed them similarly to the documents and calculated the Jaccard Index between each query and document. The top-10 results based on these similarity scores were printed for each query.

## Boolean Queries

### Create Unigram Inverted Index

Constructed from scratch with Python, no external libraries used.

**Methodology:**
- Created an empty dictionary to store the Unigram index.
- Iterated through each document, split the data into individual tokens, and inserted them into the dictionary.
- Saved the Unigram using Python’s `pickle` module.

### Save and Load Unigram Inverted Index

Utilized Python’s `pickle` module for saving and loading.

### Support for Operations

- Implemented support for T1 AND T2, T1 AND NOT T2, T1 OR T2, T1 OR NOT T2.
   
### Generalized Queries

Provided support for queries like T1 AND T2 OR T3 OR T4 ....

### Minimum Number of Comparisons

Computed the minimum number of comparisons required for query execution.

### Input Format

- The first line contains N denoting the number of queries to execute.
- The next 2N lines contain queries in the specified format.

### Output Format

- 4N lines consisting of the results.

### Perform Preprocessing Steps on Input Sequence.

## Phrase Queries

### Create Bigram Inverted Index

Constructed from scratch with Python, no external libraries used.

**Methodology:**
- Similar methodology to UNIGRAM but used consecutive token pairs as keys.

### Save and Load Bigram Inverted Index

Utilized Python’s `pickle` module for saving and loading.

### Create Positional Index

Constructed from scratch with Python, no external libraries used.

**Methodology:**
- Constructed a dictionary and corresponding positional indexes.
- Word in the dictionary was an object with properties: word value, count, and a dictionary of doc_id to doc object.
- Doc object stored the positions.

### Save and Load Positional Index

Utilized Python’s `pickle` module for saving and loading.

### Compare and Comment on Results

Compared and commented on the results obtained using Bigram Inverted Index and Positional Index.

---

## Conclusion

In this project, we successfully implemented data preprocessing, TF-IDF matrix generation, unigram and bigram inverted index construction, and positional indexing. The provided report outlines the methodologies, assumptions, and general structure of the project.

## Code

The entire project was implemented using Jupyter Notebooks in Python. Each section of the project was completed in its respective notebook. The code for each part can be accessed in the provided Jupyter notebooks for detailed implementation and execution.
