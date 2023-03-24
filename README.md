# Data Science Mission - ESCO classification

## Introduction 

This notebook contains code that scrapes data from the  European Skills, Competences, and Occupation (ESCO) database's API.  
It then creates clean DataFrame used for a more flexible classification solution to enable the creation of a hierarchy in AI & Data Science.  
This works aims at building one of the basic block for the datacraft's PhD platform project. It is to be used for future and analysis. 

This work was carried out as part of a Data Science mission at EM Lyon by Banthita Boonpun, Nathan Destrez, Sharma Kriti and Bohan Wang, under the supervision of Marie Joubert and Julien Capitaine.


## Setup 
Set up Python and install the necessary packages as described below. 
 - Python version 3.9
 - Requirements: the required imports and installations for this notebook can be found in the 'requirements.txt' file. To install them, run the following command:  `pip install -r requirements.txt`


## Notebook structure

### Data source 

The [European Skills, Competences, and Occupation (ESCO)](https://esco.ec.europa.eu/en) website is used to scrape data via its API.
ESCO is the **multilingual classification** of European Skills, Competences, Qualifications and Occupations, available in 25 European languages. It is part of the Europe 2020 strategy.
It identifies and categorises skills, competences, qualifications and occupations relevant for the EU labour market and education and training. The system provides occupational profiles and systematically shows the relationships between the different concepts (occupations, skills and competences).  
The aim of ESCO is to **support job mobility across Europe and therefore a more integrated and efficient labour market**.  
The detailed presentation of ESCO can be found here. ([link](https://esco.ec.europa.eu/en/about-esco)).

As a last note, one of ESCO's objective is to give a clear view of all the training institutions (universities, schools, etc) landscape across all of the EU.
However, as of March 2023, we found that this mapping was not sufficiently structured and did not go into enough detail about the various training courses. This is why we decided to abandon it and to focus on the classification of jobs and skills. 


### Scraping

First we request the API entry points for the occupations. That produces an output of 3008 occupations which we filter out by keywords related to data science domains.
For the rest of the notebook, the work is based on a list of 14 occupations, but the generalization to a different list of occupations is straightforward. 
From the output, each of these occupations has a link with an HTML reference to its detailed resource in the database. These references are then used to extract the information of the occupation with, among other thing:
 - a short presentation of its role,
 - a list of preferred and alternative labels in all european languages,
 - a list of all related skills typed as essential or optional.

These are basically the information we retrieve to build our own graph database using the Neo4j technology.

Note: In future work, other information may be important and future users should be aware of all the quantities that available to think about further improvements.

### Neo4j

This part of the notebook is dedicated to the construction of the Neo4j database. It mainly consists of Cypher queries run from Python.  
The design of the database is presented with the following schema:



## Acknowledgments
Mentors: Julien Capitaine & Marie Joubert 
Franck Jaotombo
Imene Brigui-Chtioui  

