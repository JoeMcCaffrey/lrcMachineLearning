# Spam Filter

This is an example of the Naive Bayes spam filter used on lrcnews.com to eliminate sponsored click-bait headlines from news APIs.

### The Data

- The badLinks.txt contain examples of spam links used to train the classifier.
Ex.

		> 9 terrible habits you need to stop immediately
		> Here's what you should never do after a work-out
		> Quiz: How long will you live?
	
The spam links all seem suspicious 
	
- The hamlinks contain examples of legitimate news headlines
	
### How to Run
- Developed and tested with Python 2.7.13
- First install dependencies:

		$ pip install -U textblob
		$ python -m textblob.download_corpora
To Run:
	
		$ python SpamFilter.py

### Output
In this example the spam filter is checking the headline:

	"D.C. court rules tracking phones without a warrant is unconstitutional"

The output from the classifier:
	
	$ The text is Spam:  neg
	Percentage of pos result:  0.01
	Percentage of neg result:  0.99
	Most Informative Features
           contains(you) = True              pos : neg    =      8.4 : 1.0
           contains(How) = True              pos : neg    =      7.6 : 1.0
           contains(all) = True              pos : neg    =      5.9 : 1.0
           contains(n't) = True              pos : neg    =      4.2 : 1.0
          contains(what) = True              pos : neg    =      4.2 : 1.0

The classifer is telling us that the headline is not spam and it is 99% certain.

The classifier also told us what the most important features are of the training data set.

**In the spam example above 3/3 links contain "you"**