# apriori-agorithm-python

[![Build Status](https://travis-ci.org/coorty/apriori-agorithm-python.svg?branch=master)](https://travis-ci.org/coorty/apriori-agorithm-python)

An Effectively Python Implementation of Apriori Algorithm for Finding Frequent sets and Association Rules

# List of files

1. data/transaction.csv: input file
2. apriori.py: define a class **Apriori**
3. test\_apriori\_command\_line.py: test the apriori algorithm


# Dataset

Your should input path of a csv file, which may seems like:

    Bread,Milk 
	Bread,Diapers,Beer,Eggs
	Milk,Diapers,Beer,Cola
	Bread,Milk,Diapers,Beer
	Bread,Milk,Diapers,Cola
	Bread,Milk
	Bread,Cola,Beer,Milk
	Milk,Bread,Beer,Cola
	Bread,Milk,Diapers,Beer
	Bread,Beer,Diapers,Diapers

Each line is a transaction, seperated by comma (,).

# Usage

To run the program with dataset provided (in ./data/) and mininum support = 0.12, mininum confidence = 0.5 and return rules for `Bread`: 

	python test_apriori_command_line.py -f ./data/transaction.csv -s 0.20 -c 0.50 -r Bread

which produce results below:
	
	frequent 1-term set:
	--------------------
	['Diapers']
	['Beer']
	['Cola']
	['Bread']
	['Milk']

	frequent 2-term set:
	--------------------
	['Diapers', 'Beer']
	['Milk', 'Bread']
	['Diapers', 'Bread']
	['Diapers', 'Milk']
	['Bread', 'Cola']
	['Bread', 'Beer']
	['Milk', 'Cola']
	['Cola', 'Beer']
	['Milk', 'Beer']
	
	frequent 3-term set:
	--------------------
	['Milk', 'Cola', 'Beer']
	['Milk', 'Bread', 'Cola']
	['Milk', 'Bread', 'Beer']
	['Diapers', 'Milk', 'Bread']
	['Diapers', 'Bread', 'Beer']
	['Diapers', 'Milk', 'Beer']
	
	==============================
	rules refer to ['Bread']
	['Milk'] -> ['Bread']: 0.8749999999999999
	['Diapers'] -> ['Bread']: 0.8333333333333334
	['Cola'] -> ['Bread']: 0.7499999999999999
	['Beer'] -> ['Bread']: 0.8571428571428572
	['Milk', 'Cola'] -> ['Bread']: 0.7499999999999999
	['Milk', 'Beer'] -> ['Bread']: 0.8
	['Diapers', 'Milk'] -> ['Bread']: 0.7499999999999999
	['Diapers', 'Beer'] -> ['Bread']: 0.8



# Reference

> *Agrawal R, Srikant R. Fast algorithms for mining association rules[C]//Proc. 20th int. conf. very large data bases, VLDB. 1994, 1215: 487-499.*


# License

MIT-License