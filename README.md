TAGME reproducibility
=====================

This repository contains resources developed within the following paper:

	F. Hasibi, K. Balog, and S.E. Bratsberg. “On the reproducibility of the TAGME Entity Linking System”, 
	In proceedings of 38th European Conference on Information Retrieval (ECIR ’16), March 2016.
	
This paper is an effort on reproducing the results presented in [1].
We received invaluable comments from the TAGME authors about their system, which are available at ``authors_comments.md``.
These comments facilitate future efforts on re-implementation of TAGME system, as they cannot be found in the original paper.


This repository is structured as follows:
  
- `nordlys/`: Code required for running entity linkers.
- `scripts/`: Evaluation scripts.
- `run-scripts.sh`: All the scripts for getting the results of the paper.
- ``authors_comments.md``: Comments of the authors of the TAGME paper [1] and notes about our experiments.

Other resources involved in this project are [data](http://hasibi.com/files/res/data.tar.gz), [qrels](http://hasibi.com/files/res/qrels.tar.gz), and [runs](http://hasibi.com/files/res/runs.tar.gz), which are described below.

**Note:** Before running the code (`run-scripts.sh`), please read the `setup.md` file and build all the required resources.


## Data

Data can be downloaded from [here](http://hasibi.com/files/res/data.tar.gz) and contains:

  - **Wiki-disamb30** and **Wiki-annot30**: The original datasets are published [here](http://acube.di.unipi.it/tagme-dataset/). As the original datasets do not contain snippets IDs, we assigned numerical IDs to the snippets.
  - **ERD-dev**: The dataset is originally published by the [ERD Challenge](http://web-ngram.research.microsoft.com/ERD2014), and we use it for generalizability experiments. The files related to this dataset have the prefix `Trec_beta`.
  - **Y-ERD**: This dataset is originally published in [2] and is available [here](http://bit.ly/ictir2015-elq). The dataset is used for generalizability experiments.
  - **Freebase snapshot**: A snapshot of Freebase containing only proper noun entities (e.g., people and locations) is published by the ERD challenge and is used for filtering entities in the generalizability experiments.


## Qrels

The qrel files can be downloaded from [here](http://hasibi.com/files/res/qrels.tar.gz). All qrels are tab-delimited and their format is as follows:

  - **Wiki-disamb30** and **Wiki-annot30**: The columns represent: snippet ID, confidence score, Wikipedia URI, and Wikipedia page id. The last column is not considered in the evaluation scripts.
  - **ERD-dev** and **Y-ERD**: The columns represent: query ID and confidence score (always 1), and Wikipedia URI. All the entities after the second column represent the interpretation set (entity set) of the query.



## Runs

The run files can be downloaded from [here](http://hasibi.com/files/res/runs.tar.gz), and categorized into two groups: reproducibility and generalizability. 

  - **Reproducibility**: The naming convention for these files is *XX_YY.txt*, where XX represents the dataset and YY is the name of the method. For each file, only the first 4 columns are considered for the evaluation, which are: snippet ID, confidence score, Wikipedia URI, and mention.
  - **Generalizability**: These files are named as *XX_YY_ZZ.elq*, where XX is the dataset, YY is the name of the method, and ZZ is the entity linking threshold used for evaluation. The format of these files is similar to the corresponding qrel files.


Contact
-------

If you have any questions, feel free to contact Faegheh Hasibi at <faegheh.hasibi@idi.ntnu.no>.

```
[1] P. Ferragina and U. Scaiella. TAGME: On-the-fly annotation of short text fragments (by Wikipedia entities). In Proceedings of CIKM '10, pages 1625–1628, 2010.
[2] F. Hasibi, K. Balog, and S. E. Bratsberg. Entity Linking in Queries: Tasks and Evaluation. In Proceedings of ICTIR ’15, pages 171–180, 2015.
```
