
Input:
From the Hugging Face README provided in “# README,” extract and output only the Python code required for execution. Do not output any other information. In particular, if no implementation method is described, output an empty string.

# README
---
dataset_info:
  features:
  - name: src
    sequence: string
  - name: tgt
    sequence: string
  - name: labels
    sequence: int64
  splits:
  - name: test
    num_bytes: 53831114
    num_examples: 11490
  - name: train
    num_bytes: 1376640992
    num_examples: 287113
  - name: validation
    num_bytes: 62200550
    num_examples: 13368
  download_size: 857262516
  dataset_size: 1492672656
license: mit
task_categories:
- summarization
language:
- en
size_categories:
- 100K<n<1M
---
## Data Card for Extractive CNN/DailyMail Dataset

### Overview
This is an extractive version of the [CNN/Dailymail](https://huggingface.co/datasets/cnn_dailymail) dataset. The structure of this dataset is identical to the original except for a minor modification in the data representation and the introduction of labels to denote the extractive summary.

The labels are generated following a greedy algorithm, as proposed by [Liu (2019)](https://arxiv.org/abs/1903.10318). The curation process can be found in the [bertsum-hf](https://github.com/eReverter/bertsum-hf) repository. I am uploading it in case someone does not want to go through the preprocessing, although Liu has a version ready for training in its [bertsum](https://github.com/nlpyang/BertSum) repository!

In this dataset:
- 'src' corresponds to 'article',
- 'tgt' equates to 'abstract',
- 'labels' represents a mapping of sentences forming the extractive summary.

### Data Architecture

Each entry in the dataset contains the following fields:
- `id`: a unique `string` identifier for each example.
- `src`: a `list[string]` field representing the original news article. Each string in the list is a separate sentence from the article.
- `tgt`: a `list[string]` field representing the professionally edited highlights or abstract of the article.
- `labels`: a `list[bool]` field with binary values. Each boolean value corresponds to a sentence in 'article', indicating whether that sentence is part of the extractive summary (1 for True, 0 for False).

### Sample Data Entry
Here is an illustrative example from the dataset:

```json
{
"id": "1",
"src": ["This is the first sentence",
"This is the second"],
"tgt": ["This is one of the highlights"],
"labels": [1, 0]
}
```

In this example, the first sentence of the article is selected as part of the extractive summary (as indicated by '1' in the 'labels'), while the second sentence is not ('0' in the 'labels').

### Usage

The extractive CNN/DailyMail dataset can be used to train and evaluate models for extractive text summarization tasks. It allows models to learn to predict which sentences from an original text contribute to a summary, providing a binary mapping as a reference. The 'tgt' or 'abstract' field can serve as a basis for comparison, helping to assess how well the selected sentences cover the key points in the abstract.
Output:
{
    "extracted_code": ""
}
