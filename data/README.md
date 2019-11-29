# Datasets

## MCQL
(**TL;DR**) The data used for training ranking model can be located under folder `mcql_processed`, including `train_neg.json`, `valid_neg.json`, `test_neg.json`, and `vocab.txt`.

### Description
Check below for a summary of data files, corresponding to Table 1 in the paper.

File           | Content   | Size | Description | 
--|--|--|--
train_neg.json | MCQs | 5999 |Training set|
valid_neg.json | MCQs | 554  | Validation set |
test_neg.json  | MCQs | 563  |Test set |
vocab.txt      | Distractors | 16446 |Candidate distractors | 

`*_neg.json` files are MCQL training/validation/test sets. Each item in the JSON file corresponds to a MCQ.
There are four fields asccociated with each question: *sentence*, *answer*, *distractors*, and *neg_samples*.
Here the number of negative examples is set to be equal to the number of distractors.
`train_neg.json` is the training data used in the paper.

**Notes**: 
* To do ranking evaluation on `valid_neg.json` and `test_neg.json` (as described in the paper),
whole vobaculary (`vocab.txt`) should be used. In other words, the *neg_samples* field in valid/test files should not be used for ranking evaluation.
* Remember to decode using utf8 when loading the vocabulary

### How to reproduce MCQL data from crawled questions?
The 7.1K MCQs crawled can be located under folder `mcql`. The following command can convert the data into a format for ranking models.
```shell
python prep_dataset.py -dataset mcql -data_dir mcql -out_dir mcql_processed
```



    ```

    
## References
Please cite the following papers if you use this data.

For MCQL
```
@inproceedings{Liang2018distractor,
  author = {Liang, Chen and
            Yang, Xiao and
            Dave, Neisarg and
            Wham, Drew and
            Pursel, Bart and
            Giles, C. Lee},
  title={Distractor Generation for Multiple Choice Questions Using Learning to Rank},
  booktitle = {Proceedings of the 13th Workshop on Innovative Use of NLP for Building Educational Applications, BEA@NAACL},
  pages={To appear},
  year={2018},
  organization={ACL}
}
```

For SciQ
```
@inproceedings{DBLP:conf/aclnut/WelblLG17,
  author    = {Johannes Welbl and
               Nelson F. Liu and
               Matt Gardner},
  title     = {Crowdsourcing Multiple Choice Science Questions},
  booktitle = {Proceedings of the 3rd Workshop on Noisy User-generated Text, NUT@EMNLP},
  pages     = {94--106},
  year      = {2017},
  organization={ACL}
}
```
