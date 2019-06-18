# The NEEQ Annual Reports Data

## Introduction
The data file company-profiles.txt contains 20040 records that are crawled and manually cleaned from the Chinese National Equities Exchange and Quotations (NEEQ) system: http://www.neeq.com.cn/. Each record has 4 columns: the annual report id, release time, company code, content. Data is collected from 2015-01-01 to 2018-01-01, covering three years (2014 to 2017).

Note that some companies release two copies of reports annually. And for new companies listed from, say 2015, the 2014 report will be missing.

## Usage
Data can be parsed using the following snippet.
```python
def parse_data(filename): 
	with open(filename, "r", encoding="utf-8") as f:
		split_lines = [line.strip().split("\t") for line in f]
	id2content = {sl[0]: sl[3] for sl in split_lines}
	id2company = {sl[0]: sl[2] for sl in split_lines}
	return id2content, id2company
```

## Citation
The paper that introduces this dataset and where more details can be found is:

H. Bai, F. Z. Xing, E. Cambria, W. B. Huang. Business Taxonomy Construction Using Concept-Level Hierarchical Clustering. In The First Workshop on Financial Technology and Natural Language Processing, FinNLP@IJCAI, 2019.

Please cite if you find this dataset useful in your research.
