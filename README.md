# Can Question Generation Debias Question Answering Models? A Case Study on Question–Context Lexical Overlap

<div align="center">
  <img width="900" alt="mrqa2021poster" src="https://user-images.githubusercontent.com/16998772/143994770-2b86ce66-3e54-4ea1-aff2-fe72950a7117.png">
</div>

- This repository contains the official dataset used in our paper:
  - [[paper](https://aclanthology.org/2021.mrqa-1.6/)] [[arXiv](https://arxiv.org/abs/2109.11256)] [[poster](https://github.com/KazutoshiShinoda/slides/blob/master/MRQA2021.pdf)]


- `squad-du-train-with-synonym-replacement.json`
  - This is our synthetic dataset used for data augmentation. This is created from the SQuAD Du Train set with synonym replecement.

- If you want to reproduce our experiment, please download the squad du split from
  - https://github.com/tomhosking/squad-du-split
- and train QA models first on our `squad-du-train-with-synonym-replacement.json`, and second on the train-v1.1.json from the squad-du-split repo.

- For the evaluation with Hard/Easy split, please use `overlap_dev.json` and `overlap_test.json`, where the question-context lexical overlap for each data point in squad du dev/test split is stored like:

```
[
  qa_id_0: question-context lexical overlap,
  qa_id_1: question-context lexical overlap,
  ...
]
```

- In our experiment, if lexical overlap <= 0.3, then it is classified as Hard; otherwise, it is classified as Easy.

- If you use our dataset, please cite our paper using this bibtex:

```
@inproceedings{shinoda-etal-2021-question,
    title = "Can Question Generation Debias Question Answering Models? A Case Study on Question{--}Context Lexical Overlap",
    author = "Shinoda, Kazutoshi  and
      Sugawara, Saku  and
      Aizawa, Akiko",
    booktitle = "Proceedings of the 3rd Workshop on Machine Reading for Question Answering",
    month = nov,
    year = "2021",
    address = "Punta Cana, Dominican Republic",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2021.mrqa-1.6",
    pages = "63--72",
    abstract = "Question answering (QA) models for reading comprehension have been demonstrated to exploit unintended dataset biases such as question{--}context lexical overlap. This hinders QA models from generalizing to under-represented samples such as questions with low lexical overlap. Question generation (QG), a method for augmenting QA datasets, can be a solution for such performance degradation if QG can properly debias QA datasets. However, we discover that recent neural QG models are biased towards generating questions with high lexical overlap, which can amplify the dataset bias. Moreover, our analysis reveals that data augmentation with these QG models frequently impairs the performance on questions with low lexical overlap, while improving that on questions with high lexical overlap. To address this problem, we use a synonym replacement-based approach to augment questions with low lexical overlap. We demonstrate that the proposed data augmentation approach is simple yet effective to mitigate the degradation problem with only 70k synthetic examples.",
}
```
