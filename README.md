Download Link: https://assignmentchef.com/product/solved-snlp-exercise-8
<br>
<h2>1      Feature Selection</h2>

<h3>1.1                      Pointwise Mutual Iinformation</h3>

In this exercise you will perform feature selection using Pointwise Mutual Information (PMI).

Extract the archive movie_review_data.zip provided together with the excercise sheet. It contains 2 directories with positive and negative movie reviews. You should extract the text and remove all non-alphanumeric characters including punctuation and stopwords defined in nltk (use stopwords from nltk.corpus).

Extract all unigrams and bigrams for positive and negative reviews. Note that you should also filter out all bigrams when at least one of the words appears in the stopword list.

Compute PMI for unigrams which occur at least 100 times in the corpus and report the top 20 values with the corresponding words for the positive class and top 20 values for the negative class. Do the same for bigrams but use 50 occurrences as the frequency threshold and compare the results. Can you predict whether the unigrams and bigrams with the highest PMI values come from the positive or negative reviews judging from the words alone? Why do we need to filter out low frequency words? What would happen if we considered all words in the corpus for the PMI calculation?

Also compare PMI and frequency values of word <em>good </em>versus <em>bad </em>for both positive and negative classes. Which difference do you observe?

<h3>1.2                       Chi-square Test</h3>

Assume that you have the following counts of words {<em>good</em>, <em>interesting</em>} and {<em>nice</em>, <em>entertaining</em>} from the movie reviews as shown in Table 1.

<table width="430">

 <tbody>

  <tr>

   <td width="210">


    <table width="202">

     <tbody>

      <tr>

       <td width="77"> </td>

       <td width="61">positive</td>

       <td width="64">negative</td>

      </tr>

      <tr>

       <td width="77">good</td>

       <td width="61">7397</td>

       <td width="64">7159</td>

      </tr>

      <tr>

       <td width="77">interesting</td>

       <td width="61">1449</td>

       <td width="64">1603</td>

      </tr>

     </tbody>

    </table></td>

   <td width="219">


    <table width="210">

     <tbody>

      <tr>

       <td width="86"> </td>

       <td width="61">positive</td>

       <td width="64">negative</td>

      </tr>

      <tr>

       <td width="86">nice</td>

       <td width="61">1105</td>

       <td width="64">854</td>

      </tr>

      <tr>

       <td width="86">entertaining</td>

       <td width="61">817</td>

       <td width="64">558</td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Table 1: Observed counts

Use the Chi-square test to find out whether the distributions of two different sets of words: {<em>good </em>and <em>interesting</em>} and {<em>nice </em>and <em>entertaining</em>} depend on the type of movie reviews (positive vs negative). In other words, you will use test statistics to check whether the distribution depends on the category.

Your solution should include the computation of the Chi-square value and the corresponding p-value for alpha=0.05.

<h2>2      Classification</h2>

<h3>2.1                      Support Vector Machine</h3>

In this exercise you will implement a sentiment classifier using Support Vector Machine (SVM). Use the dataset from movie_review_data.zip which you explored in the previous exercise. Using the same pre-processing steps as specified in part 1, extract unigrams and bigrams and apply CountVectorizer from the sklearn library<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. This will allow you to generate features for the classifier.

Divide the data into training (80%) and test (20%) sets. You can use train_test_split from sklearn.model_selection.

Train SVM classifier with linear kernel using only unigrams as features and report the accuracy scores on the test set. Create another classifier using bigrams as features and compare its performance to the unigram-based classifier. For each case provide a confusion matrix which shows number of correctly and incorrectly classified instances of each class.

You should also experiment with different values of the regularization parameter <em>C </em>(e.g. using a range of values between 0.5 and 1 for the parameter tuning). Briefly explain the impact of the parameter choice on the classification.

Apply tf-idf<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> to the counts and compare SVM performance with simple counts to the results obtained with tf-idf counts.

<strong>Note: </strong>In case the computation is very slow on your computer, reduce the corpus size by removing the equal proportion of positive and negative reviews and mention any modifications in the report.

<h3>2.2                       Different Classifiers</h3>

Use one classifier of your choice: Decision Tree, Maximum Entropy (Logistic Regression) or Multinomial Bayes to perform the classification<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a>. Briefly describe how the classifier works and which parameters it needs (if any) and compare the results to the SVM performance. In which situation it is optimal to use the selected classifier and in which situation it is not a good choice?

<a href="#_ftnref1" name="_ftn1"></a>