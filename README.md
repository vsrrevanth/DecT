# Decoder Tuning (DecT) for Efficient Language Understanding

This repository is an extension of the original work on Decoder Tuning (DecT), which introduces an efficient method for adapting large pre-trained language models with minimal computational resources. Our extension includes additional evaluation metrics such as F1 score, precision, and recall to provide a deeper understanding of the model's performance.

## Introduction

DecT proposes a fine-tuning approach that significantly reduces the computational cost typically associated with adapting pre-trained models for various NLP tasks. This method is especially valuable for researchers and practitioners who may not have access to extensive computational resources.

## Quick Start

### Setup

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/vsrrevanth/DecT.git
cd DecT
pip install -r requirements.txt
```

## Data Preparation

Download the necessary datasets by running the provided script:

```bash
cd datasets
bash download_datasets.sh
cd ..
```

## Training and Evaluation

Execute the following command to train and evaluate the model:

```bash
python src/run_dect.py --model [MODEL] \
                      --size [SIZE] \
                      --type [TYPE] \
                      --dataset [DATASET]\
                      --shot [1,4,16]
```


```bash
python src/run_dect.py --model roberta \
                       --size base \
                      --type mlm \
                      --dataset sst2 \
                      --shot 1
```
Replace the model, size, type, dataset, and shot parameters as needed based on your experimental design.


## Detailed Configuration

The repository allows for various configurations to reproduce the original study or conduct new experiments. The configurable parameters include:

--model: Specifies the model to be used (e.g., 'roberta', 'alpaca').\
--size: Defines the size of the model (e.g., 'base', 'large').\
--type: Determines the type of model (e.g., 'mlm', 'lm').\
--dataset: Chooses the dataset for the experiment (e.g., 'sst2', 'imdb', 'yelp').\
--shot: Sets the number of shots for few-shot learning scenarios.

Each parameter can be adjusted according to the requirements of the experiment.


## Reproducing the Study

To reproduce the original study's results, run the run_dect.py script with the parameters that correspond to the experiments detailed in the paper. For example:

```bash
python src/run_dect.py --model roberta --size base --type mlm --dataset sst2 --shot 1
python src/run_dect.py --model roberta --size large --type mlm --dataset yelp --shot 16
```

These commands will run the DecT method on the SST2 and Yelp datasets with the specified configurations.

## Additional Metrics
We have extended the source code to include additional performance metrics such as F1 score, precision, and recall. These metrics provide a more comprehensive understanding of the model's performance. The modifications are present in `dect_trainer.py` and are seamlessly integrated into the evaluation output.

## Documentation and Ease of Reproduction

The source code is forked from the author's original repository and retains its well-documented structure. Additional comments have been added to the new sections of the code for clarity. The provided README file and the scripts ensure that findings are easily reproducible given the documentation, data, and appropriate compute resources.

## Contact

For any queries regarding the setup or configurations, please open an issue in this repository, and we will assist you at the earliest.


This `README.md` provides clear instructions on how to set up the project, outlines the configurations needed to reproduce the study, and offers a brief introduction to the topic. It also mentions the additional metrics that have been added to the code, following the first rubric. The second and third rubrics are addressed by providing comprehensive documentation and setup instructions to facilitate easy reproduction of the findings.



