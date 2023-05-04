Download Link: https://assignmentchef.com/product/solved-csci2270-homework1-array-doubling-with-dynamic-memory
<br>
<strong>Array doubling with dynamic memory</strong>

In this assignment, we will write a program to analyze the word frequency in a document. Because the number of words in the document may not be known a priori, we will implement a <strong>dynamically doubling array </strong>to store the necessary information.​

Please read all the directions <em>before</em>​ ​writing code, as this write-up contains specific requirements for how the code should be written.




<table>

 <tbody>

  <tr>

   <td width="32"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<h1>Your Task</h1>

There are two files on Moodle. One contains text to be read and analyzed by your program, and is named <strong><em>mobydick.txt</em></strong>​ ​. As the name implies, this file contains the full text from <em>Moby</em>​<em> Dick</em>​. For your convenience, all the punctuation has been removed, all the words have been converted to lowercase, and the entire document can be read as if it were written on a single line. The other file contains the 50 most common words in the English language, which your program will ignore during analysis . It is called <strong><em>ignoreWords.txt</em></strong>​ ​.

Your program must take three command line arguments in the following order – a number <em>N</em>​ ​, the name of the text to be read, and the name of the text file with the words that should be ignored. It will read the text (<strong>ignoring</strong>​<strong> the words in the second file</strong>)​ and store all distinct words in a dynamically doubling array (<strong>For</strong>​<strong> file I/O, refer to your first homework assignment…</strong>)​ . It should then calculate and print the following information:

<ul>

 <li>The number of times array doubling was required to store all the distinct words</li>

 <li>The number of distinct “non-ignore” words in the file</li>

 <li>The total word count of the file (excluding the ignore words)</li>

</ul>




<ul>

 <li>Starting from index N, print the 10 most frequent words along with their probability (<strong><em>up to</em></strong>​</li>

</ul>

<strong><em>4 decimal places</em></strong>​) of occurrence from the array. The array should be sorted in decreasing order based on probability of occurrence of the words.  If two words have the same probability, then those two words should be listed in alphabetical order.




For example, running your program with the command:

would print the next 10 words starting from index 25, i.e. your program should print the 25​<sup>th</sup><sup>​</sup>-34​<sup>th </sup><sup>​</sup>most frequent words, along with their respective probabilities. Keep in mind that these words should <strong>not </strong>​ be any of the words from ​ <strong><em>ignoreWords.txt</em></strong>​ ​.

The full results would be:

<strong>Specifics: </strong>

<ol>

 <li><strong>Use an array of structs to store the words and their counts </strong></li>

</ol>

There is an unknown number of words in the file. You will store each distinct word and its count (the number of times it occurs in the document). Because of this, you will need to store these words in a dynamically sized <strong>array</strong>​<strong> of structs</strong>.​ The struct must be defined as follows:

<ol start="2">

 <li><strong>Use the array-doubling algorithm to increase the size of your array </strong></li>

</ol>

Your array will need to grow to fit the number of words in the file. <strong>Start</strong>​<strong> with an array size of 100</strong>,​ and double the size whenever the array runs out of free space. You will need to allocate your array dynamically and copy values from the old array to the new array. (Array-doubling algorithm should be implemented in <em>main() </em>​ ​function).

<ol start="3">

 <li><strong>Ignore the top 50 most common words that are read in from the second file </strong>To get useful information about word frequency, we will be ignoring the 50 most common words in the English language. These words will be read in from a file, whose name is the third command line argument.</li>

 <li><strong>Take three command line arguments </strong></li>

</ol>

Your program must take three command line arguments – a number <em>N</em>​ ​which tells your program the starting index to print the next 10 most frequent words, the name of the text file to be read and analyzed, and the name of the text file with the words that should be ignored.

<ol start="5">

 <li><strong>Output the Next 10 most frequent words starting from index N </strong></li>

</ol>

Your program should print out the next 10 most frequent words – not including the common words – starting index N in the text where <em>N</em>​ ​is passed in as a command line argument. If two words have the same frequency, then those two words should be listed in alphabetical order.

E.g. If N=5 then print words from index 5-14 in the array sorted in decreasing order of the probabilities of the occurrence of the words.

<ol start="6">

 <li><strong>Format your final output this way: </strong></li>

</ol>

For example, using the command:

you should get the output:

<ol start="7">

 <li><strong>You must include the following functions (they will be tested by the autograder): </strong></li>

 <li><strong> In your main function </strong>

  <ol>

   <li>If the correct number of command line arguments is not passed, print the below statement and exit the program</li>

  </ol></li>

</ol>







<ol>

 <li>Get ignore-words/common-words from <strong><em>txt </em></strong>​ ​and store them in an array (Call your <strong>getIgnoreWords </strong>​            <sup>function)</sup>​          iii.        Array-doubling should be done in the main() function</li>

 <li>Read words from <strong><em>mobydick.txt </em></strong>​ ​and store all distinct words that are not ignore-words in an array of structs

  <ol>

   <li>Create a dynamic <strong>wordRecord </strong>​ array of size 100​</li>

   <li>Add non-ignore words to the array (double the array size if array is</li>

  </ol></li>

</ol>

full)

<ol start="3">

 <li>Keep track of the number of times the <strong>wordRecord </strong>​ array is​            doubled and the number of distinct non-ignore words</li>

</ol>




<ol>

 <li></li>

</ol>

<strong> </strong>

This function should read the words to ignore from the file with the name stored in <strong>ignoreWordFileName</strong>​ and​ store them in the <strong>ignoreWords</strong>​ array.​ You can assume there will be exactly 50 words to ignore. There is no return value. In case the file fails to open, print an error message using the below cout statement:




This function should return whether <strong>word </strong>​          <sup>is in the </sup>​          <strong>ignoreWords</strong>​     array.




This function should compute the total number of words in the entire document by summing up all the counts of the individual distinct words. The function should return this sum.

This function should sort the <strong>distinctWords</strong>​ array​ (which contains <strong>length</strong>​ initialized elements) by word count such that the most frequent words are sorted to the beginning. The function does not return anything.







<ol>

 <li></li>

</ol>

<strong> </strong>

This function should print the next 10 words after the starting index N from <strong>sorted </strong>array​ of <strong>distinctWords</strong>​ ​. These 10 words should be printed with their probability of occurrence <strong>up</strong>​<strong> to 4 decimal places. </strong>The​ exact format of this printing is given below. The function does not return anything.




Probability of occurrence of a word at position <strong><em>ind </em></strong>​ ​in the array is computed using the formula: <strong><em>(</em></strong>​ <strong><em>Don’t forget to cast to float!) </em></strong>

<strong><em> </em></strong>

<strong><em> </em></strong>

Output format





