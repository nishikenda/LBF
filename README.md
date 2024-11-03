# Efficient Chemical Compounds Search Using Learned Bloom Filter

## Authors

- **Ken Nishida**
- **Katsuhiko Hayashi**
- **Hidetaka Kamigaito**
- **Hiroyuki Shindo**

## Abstract

As compound data volumes grow, efficient and accurate search methods are increasingly required. 
For compounds like PFAS, which face stricter regulations due to environmental and health concerns, rapid and precise search is essential. 
Conventional structure-based algorithms and fingerprint-based similarity searches face limitations in memory usage and computational time with large datasets. 
While Bloom Filter (BF) offers efficient search capabilities, it struggles with increased memory consumption as data scales.
To address this, we propose an efficient compound search method using a Learned Bloom Filter (LBF), combining machine learning with BF. 
Introduced by Kraska et al., LBF reduces unnecessary memory usage through model-based predictions, enhancing space efficiency while maintaining accuracy. 
By learning complex chemical structure patterns, LBF minimizes false positives and achieves high-precision search with lower memory consumption. 
Comparative experiments in Section \ref{sec4} show that LBF significantly reduces memory usage while maintaining accuracy, highlighting its potential in chemical safety assessments and early-stage drug screening.

## Introduction

In the field of chemical informatics, efficient search methods for large chemical compounds datasets are crucial. Traditional methods often face limitations in terms of memory usage and computational speed, especially as the size of datasets grows.

This repository contains the code and data for reproducing the experiments in our paper titled **"Efficient Chemical Compounds Search Using Learned Bloom Filter"**. We introduce a Learned Bloom Filter (LBF) that combines machine learning models with the traditional Bloom Filter to improve search efficiency and reduce memory usage.

## Contents

- **[Paper (PDF)](link-to-your-paper.pdf)**: The full paper detailing our methodology and results.
- **Code**: Implementation of the Learned Bloom Filter for Chemical compounds
- **Datasets**: The datasets used in the experiments, including PFAS and PCBA datasets.
- **Figures and Tables**: Visual representations of the experimental results.

## Getting Started

### Prerequisites

- Python 3.6 or higher
- Required Python libraries (listed in `requirements.txt`)

### Installation

Clone the repository and install the required packages:

```bash
git clone https://github.com/nishikenda/lbf.git
cd lbf
pip install -r requirements.txt


## Datasets

We provide the datasets used in our experiments:

- **PFAS Dataset**: Harmful chemical compounds with adverse environmental and health effects.
- **PCBA Dataset**: Biological activity data for molecules from PubChem BioAssays.

The datasets are available in the `datasets` directory.

## Running the Experiments

To reproduce the experiments from the paper, you can run the main script with the desired parameters. For example:

```bash
python main.py --dataset PFAS --max_seq_length 75 --hidden_size 64 --learning_rate 0.0005 --epochs 50 --bf_fp_prob 0.01
```

Replace the `--dataset` parameter with `PCBA` to run experiments on the PCBA dataset.

### Parameters

- `--dataset`: Name of the dataset (`PFAS` or `PCBA`).
- `--max_seq_length`: Maximum sequence length for SMILES strings.
- `--hidden_size`: Hidden layer size for the RNN model.
- `--learning_rate`: Learning rate for training the model.
- `--epochs`: Number of training epochs.
- `--bf_fp_prob`: Desired false positive probability for the Bloom Filter.


## Citation

If you use this code or datasets in your research, please cite our paper:

```bibtex
@article{XXX,
  title={Efficient Chemical Compounds Search Using Learned Bloom Filter},
  author={Nishida, Ken and Hayashi, Katsuhiko and Kamigaito, Hidetaka and Shindo, Hiroyuki},
  year={XXX},
  volume={XX},
  number={X},
  pages={XX--XX}
}
```

## Acknowledgments

We would like to thank all contributors and the community for their support.

## Contact

For any questions or inquiries, please contact:

- **Ken Nishida**: [kenmankita@eis.hokudai.ac.jp](mailto:ken.nishida@example.com)

**Note**: Please ensure to replace placeholders like `link-to-your-paper.pdf`, `ken.nishida@example.com`, and any other placeholders with actual information relevant to your repository.

## References

1. Kraska et al., "The Case for Learned Index Structures", 2018.
2. Medina et al., "Bloom Filter Molecules: Fast Chemical Similarity Search Using Bloom Filters", 2023.
3. Weininger, D., "SMILES, a chemical language and information system. 1. Introduction to methodology and encoding rules", 1988.
4. O'Boyle, N.M., "Towards a Universal SMILES Representation - A Standard Method to Generate Canonical SMILES Based on the InChI", 2012.

- **PFAS Dataset**: Contains SMILES representations of per- and polyfluoroalkyl substances, known for their persistence in the environment.
- **PCBA Dataset**: PubChem BioAssay dataset containing biological activity data for various molecules.

---

Please feel free to explore the repository and utilize the resources provided. Contributions and feedback are welcome!

