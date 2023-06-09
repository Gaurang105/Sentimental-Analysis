# Sentimental-Analysis

## article_scraper.ipynb ##

This Python code is used to scrape articles from URLs specified in an Excel file 
and save the scraped content as text files. The code reads the input file and creates 
a folder named 'scraped-articles' to store the output files. It then loops through each 
row in the Excel file, retrieves the corresponding URL using the requests package, and 
extracts the article content using the BeautifulSoup package. The code checks for the 
presence of an 'h1' tag and extracts its text as the title of the article. It then 
searches for 'p' tags within the specified CSS selectors and extracts the text content 
from each 'p' tag. The code saves the extracted title and article content as a text file
 in the 'scraped-articles' folder with a file name corresponding to the 'URL_ID' value in
the input Excel file.


## cleaning_stopwords.ipynb ##

This Python code is used to remove stopwords from text files containing scraped article content. 
The code loads stopwords from multiple text files in a specified folder and creates a list of all 
stopwords. It then iterates over all text files in a specified directory (presumably containing scraped article content), 
reads the contents of each file, removes stopwords from the text, and overwrites the file with the cleaned text.

Specifically, the code loads stopwords from multiple files in a specified folder using a loop that reads each 
file and appends its stopwords to a list. It then sets the article directory and iterates over all files in 
that directory. For each file, it checks if the file ends with the '.txt' extension, reads the contents of 
the file, splits the text into words, removes stopwords from the list of words, and rejoins the cleaned words 
into a single string. Finally, it overwrites the original file with the cleaned text.


## dict_positive_negative_words.ipynb ##

This Python code is used to remove stopwords from files containing positive and negative words. The code first 
sets the folder containing the stopwords files and the folder containing the positive and negative words files. 
It then creates an empty set called 'stopwords' and iterates over all files in the stopwords folder. For each 
file with a name that matches the regular expression 'StopWords\d', the code reads the contents of the file, 
splits it into lines, and adds each line as an element to the 'stopwords' set.

Next, the code iterates over the 'positive-words.txt' and 'negative-words.txt' files in the positive-negative 
words folder. For each file, the code reads the contents of the file, splits it into lines, and removes any words
that are found in the 'stopwords' set. The resulting list of words without stopwords is then written back to 
the original file, overwriting its previous contents.

In summary, this code removes stopwords from positive and negative words files by creating a set of stopwords 
from multiple stopwords files, iterating over the positive and negative words files, removing any stopwords 
from them, and overwriting the original files with the cleaned words list.


## main.ipynb ##

This Python code is used to calculate various readability and sentiment analysis metrics for a set of articles 
and save the results to an output Excel file.

The code first loads an input Excel file ('Input.xlsx') containing a list of URLs and their corresponding IDs. 
It then creates an output Excel file ('Output Data Structure.xlsx') and defines the format of the output file 
by adding column headers to the first row of the output worksheet.

Next, the code loads a set of positive and negative words from text files in a specified folder and defines a 
set of English stop words using the NLTK library. It also defines a function to count syllables in a word.

The code then processes each row of the input Excel file by reading the corresponding article from a folder 
('scraped-articles') and calculating various readability and sentiment analysis metrics for the article. The
metrics include positive score, negative score, polarity score, subjectivity score, average sentence length, 
percentage of complex words, fog index, word count, complex word count, syllables per word, personal pronouns
count, and average word length.

Finally, the code appends the results for each article to the output Excel file, one row per article. Each row
contains the URL ID, URL, and the calculated metrics for the corresponding article.

In summary, this code reads a set of URLs from an input Excel file, scrapes the corresponding articles from a folder, 
calculates various readability and sentiment analysis metrics for each article, and saves the results to an output Excel file.