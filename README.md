# Analyzing_Large_Amount_n-gram_Data_with_Pig_AWS
 Analyzing Large Amount of Data with Pig on AWS
 
 We will try out Apache Pig for processing n-gram data on Amazon Web Services (AWS). we would learn and solve it using distributed computing on Amazon EC2.
The services you will primarily be using are Amazon S3 storage, Amazon Elastic Cloud Computing (EC2) virtual servers in the cloud, and Amazon Elastic MapReduce (EMR) managed Hadoop framework.

Dataset -- http://storage.googleapis.com/books/ngrams/books/datasetsv2.html

The files in these two S3 buckets are stored in a tab (‘\t’) separated format. Each line is in the following format:

n-gram TAB year TAB occurrences TAB books NEWLINE

Some example lines:

I am        so 1936        441        90

I am        so 1945        211        25

I am        so 1951        47        12

very cool as        1923        118        10

very cool as        1980        320        100

very cool as        2012        922        302

very cool as        2017        1820        612


The above lines tell us that, in 1936, the trigram “I am so” appeared 441 times in 90 different books. In 1945, “I am so” appeared 211 times in 25 different books. And so on.



Goal
Output the 20 trigrams having the highest average number of appearances per book along with their corresponding averages, in tab-separated format, sorted in descending order. Only consider entries with at least 400 occurrences and at least 15 books. If multiple trigrams have the same average, order them alphabetically. For the example above, the output will be:


I am so        4.9                

very cool as        3.00        


Refer to the calculations given below

I am so                (441) / (90) = 4.9

very cool as        (922 + 1820) / (302 + 612) = 3.00



