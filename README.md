# NLP-GAN
Original repository :- LTR-DG
Data and code used for paper "Distractor Generation for Multiple Choice Questions Using Learning to Rank" (Liang, BEA'18). 

The goal is to predict 3 distractors for the question and its correct answer provided. The predicted distractors should have very close resemblance to the set of question and answer. Evaluation will be made on basis of consine similarity between the set and the distractors generated.

We use NLP for tokenizing the data so that pre-generated vocabulary(GloVe data) could be used on it. After which we use the attention model in order to work with the large sentences in neural network. 

Generative adverserial network(GAN) is used to predict the distractor. GAN has a distractor which takes the training data and sends the output to the generator. Generator in return produces 3 distractors which are not in the training data. It is the distractor's task to distinguish the real and fake results. the cycle repeats until the generator is able to produce results which are almost real.
## Dataset
Datasets can be found under "data".

## Code
To be updated.

## Reference
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
  pages={284--290},
  year={2018},
  organization={ACL}
}
```
