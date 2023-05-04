Download Link: https://assignmentchef.com/product/solved-cs4395-homework3-language-models
<br>
<strong>Objective</strong>: Use n-gram models for text analysis.

In this homework you will create bigram and unigram dictionaries for English, French, and Italian using the provided training data where the key is the unigram or bigram text and the value is the count of that unigram or bigram in the data. Then for the test data, calculate probabilities for each language and compare against the true labels.




<strong>Instructions</strong>:




<ol>

 <li>Program 1: Build language models for 3 languages as follows.

  <ol>

   <li>create a function with a filename as argument</li>

   <li>read in the text and remove newlines</li>

   <li>tokenize the text</li>

   <li>use nltk to create a bigrams list</li>

   <li>create a unigrams list</li>

  </ol></li>

</ol>

<table width="542">

 <tbody>

  <tr>

   <td width="275">Element</td>

   <td width="268">Points</td>

  </tr>

  <tr>

   <td width="275">Python script runs without error</td>

   <td width="268">30</td>

  </tr>

  <tr>

   <td width="275">Appropriate comments and white space</td>

   <td width="268">10</td>

  </tr>

  <tr>

   <td width="275">Program 1, 2</td>

   <td width="268">30 each</td>

  </tr>

  <tr>

   <td width="275">Total</td>

   <td width="268">100</td>

  </tr>

 </tbody>

</table>

<ol>

 <li>use the bigram list to create a bigram dictionary of bigrams and counts, [‘token1 token2’] -&gt; count</li>

 <li>use the unigram list to create a unigram dictionary of unigrams and counts,</li>

</ol>

[‘token’] -&gt; count

<ol>

 <li>return the unigram dictionary and bigram dictionary from the function</li>

 <li>in the main body of code, call the function 3 times for each training file, pickle the 6 dictionaries and save to files with appropriate names. The reason we are pickling them in one program and unpickling them in another is that NLTK ngrams is slow and if you put this all in one program you will waste a lot of time waiting for ngrams() to finish.</li>

</ol>

<ol start="2">

 <li>Program 2.

  <ol>

   <li>Read in your pickled dictionaries.</li>

   <li>For each test file, calculate a probability for each language (see note below) and write the language with the highest probability to a file.</li>

   <li>Compute and output your accuracy as the percentage of correctly classified instances in the test set. The file LangId.sol holds the correct classifications.</li>

   <li>output your accuracy, as well as the line numbers of the incorrectly classified items Grading Rubric:</li>

  </ol></li>

</ol>

Creating the dictionaries in Program 1:

You can use the NLTK ngrams() function to create a bigrams and a unigrams generator object. Then you can iterate over each to create the dictionary using Python’s .count() string method to extract counts from the text you read in.

Calculating probabilities in Program 2:

The probabilities will be large enough so that you don’t need to use logs, we will simply multiply the probabilities together. Each bigram’s probability with Laplace smoothing is: (b + 1) / (u + v)  where b is the bigram count, u is the unigram count of the first word in the bigram, and v is the total vocabulary size (add the lengths of the 3 unigram dictionaries).