
Input:
From the Hugging Face README provided in “# README,” extract and output only the Python code required for execution. Do not output any other information. In particular, if no implementation method is described, output an empty string.

# README
---
dataset_info:
  features:
  - name: id
    dtype: int64
  - name: translation
    struct:
    - name: en
      dtype: string
    - name: vi
      dtype: string
  splits:
  - name: train
    num_bytes: 2478779.1928870734
    num_examples: 10000
  - name: eval
    num_bytes: 247877.91928870731
    num_examples: 1000
  - name: test
    num_bytes: 329197
    num_examples: 1268
  download_size: 1844813
  dataset_size: 3055854.112175781
configs:
- config_name: default
  data_files:
  - split: train
    path: data/train-*
  - split: eval
    path: data/eval-*
  - split: test
    path: data/test-*
---

Output:
{
    "extracted_code": ""
}
