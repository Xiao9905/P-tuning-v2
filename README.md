# P-tuning v2

P-Tuning v2: Prompt Tuning Can Be Comparable to Finetuning Universally Across Scales and Tasks

An optimized prompt tuning strategy achieving comparable performance to fine-tuning on small/medium-sized models and sequence tagging challenges. 

P-tuning v2 leverages **deep prompt tuning**, which is to apply continuous prompts for every layer input of the pretrained transformer. 
Deep prompt tuning increases the capacity of continuous prompts and closes the gap to fine-tuning across various settings, especially for small models and hard tasks.

![](figures/P-tuning-v2.png)

## Reproduce Tips
We reimplement P-tuning v2's results on BERT-large/RoBERTa-large with:

* Ubuntu servers with NVIDIA GeForce RTX 3090 (24G) GPUs
* cuda 11.1
* packages with certain versions (provided below)

We notice that the best hyper-parameters can be sensitive to your server environment and package version. 
If you do not have the exact same environment, we highly recommend you to run hyper-parameter search in your environment
based on our example hyper-parameter search script in [search_script](search_script) and result collection scripts [search.py](search.py).

### Setup
We conduct our experiment with Anaconda3. If you have installed Anaconda3, then create the environment for P-tuning v2:

```shell
conda create -n pt2 python=3.8.5
conda activate pt2
```

After we setup basic conda environment, install pytorch related packages via:

```shell
conda install -n pt2 pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=11.0 -c pytorch
```

Finally, install other python packages we need:

```shell
pip install -r requirements.txt
```

### Data
For SuperGLUE and SQuAD datasets, we download them from the Huggingface Datasets APIs (embedded in our codes).
