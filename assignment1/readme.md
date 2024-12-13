# CS336 Spring 2024 Assignment 1: Basics

For a full description of the assignment, see the assignment handout at
[cs336_spring2024_assignment1_basics.pdf](./cs336_spring2024_assignment1_basics.pdf)

If you see any issues with the assignment handout or code, please feel free to
raise a GitHub issue or open a pull request with a fix.

## Setup

0. Set up a conda environment and install packages:

``` sh
conda create -n cs336_basics python=3.10 --yes
conda activate cs336_basics
pip install -e .'[test]'
```

1. Run unit tests:

``` sh
pytest
```

Initially, all tests should fail with `NotImplementedError`s.
To connect your implementation to the tests, complete the
functions in [./tests/adapters.py](./tests/adapters.py).

2. Download the TinyStories data and a subsample of OpenWebText:

``` sh
mkdir -p data
cd data

wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-train.txt
wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-valid.txt

wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_train.txt.gz
gunzip owt_train.txt.gz
wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_valid.txt.gz
gunzip owt_valid.txt.gz

cd ..
```

===============================================================
## Standard Transformer Language Model Checklist

- [x] **1. Overall Architecture**

- [x] **2. Byte Pair Encoding**
  - [x] 2.1. Unicode Standard
  - [x] 2.2. Unicode Encoding
  - [ ] 2.3. Subword Tokenization
  - [ ] 2.4. BPE Tokenizer Training
  - [ ] 2.5. Experimenting with BPE Tokenizer Training
  - [ ] 2.6. BPE Tokenizer: Encoding and Decoding
    - [ ] 2.6.1. Encoding Text
    - [ ] 2.6.2. Decoding Text
  - [ ] 2.7. Experiments

- [ ] **3. Transformer Model Language Architecture**
  - [ ] 3.1. Transformer LM
    - [ ] 3.1.1. Token and Positional Embeddings
    - [ ] 3.1.2. Pre-norm Transformer Block
  - [ ] 3.2. Output Normalization and Embedding
  - [ ] 3.3. Remark: Batching and Efficient Computation
  - [ ] 3.4. Pre-norm Transformer Block
    - [ ] 3.4.1. Root Mean Square Layer Normalization
    - [ ] 3.4.2. Position-wise Feed-Forward Network
    - [ ] 3.4.3. Scaled Dot Product Attention
    - [ ] 3.4.4. Causal Multi-Head Self Attention
  - [ ] 3.5. The Full Transformer LM

- [ ] **4. Training a Transformer LM**
  - [ ] 4.1. Cross-Entropy Loss
  - [ ] 4.2. SGD Optimizer
  - [ ] 4.3. AdamW
  - [ ] 4.4. Learning Rate Scheduler
  - [ ] 4.5. Gradient Clipping

- [ ] **5. Training Loop**
  - [ ] 5.1. Data Loader
  - [ ] 5.2. Checkpointing
  - [ ] 5.3. Training Loop

- [ ] **6. Generating Text**

- [ ] **7. Experiments**
  - [ ] 7.1. How to Run Experiments and Deliverables
  - [ ] 7.2. TinyStories
  - [ ] 7.3. Ablations and Architecture Modifications
  - [ ] 7.4. Running on OpenWebText