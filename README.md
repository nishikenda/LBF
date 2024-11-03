# Efficient Chemical Compounds Search Using Learned Bloom Filter

## Authors

- **Ken Nishida**
- **Katsuhiko Hayashi**
- **Hidetaka Kamigaito**
- **Hiroyuki Shindo**

## Abstract

As the size of chemical compounds datasets continues to expand, the need for both efficient and precise search methods has become increasingly evident. Traditional search techniques, while widely used, face significant challenges in terms of memory consumption and computational efficiency, particularly when dealing with large-scale chemical compounds datasets. This issue is particularly evident with chemical compounds such as PFAS, which have become subject to tighter regulations owing to growing concerns regarding their environmental and health impacts.

To address these challenges, this study proposes an efficient chemical compounds search method using the Learned Bloom Filter (LBF), a combination of machine learning models and the traditional Bloom Filter (BF). LBF reduces unnecessary memory consumption through model-based predictions, improving overall performance. Our study evaluates the effectiveness of LBF by comparing it with standard BF. The experimental results reveal that LBF significantly improves spatial efficiency and reduces false positive rates, all while maintaining a high level of search accuracy.

## Introduction

In the field of chemical informatics, efficient search methods for large chemical compounds datasets are crucial. Traditional methods often face limitations in terms of memory usage and computational speed, especially as the size of datasets grows.

This repository contains the code and data for reproducing the experiments in our paper titled **"Efficient Chemical Compounds Search Using Learned Bloom Filter"**. We introduce a Learned Bloom Filter (LBF) that combines machine learning models with the traditional Bloom Filter to improve search efficiency and reduce memory usage.

## Contents

- **[Paper (PDF)](link-to-your-paper.pdf)**: The full paper detailing our methodology and results.
- **Code**: Implementation of the Learned Bloom Filter using a Recurrent Neural Network (RNN) and comparison with the standard Bloom Filter.
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

## Results

The results of the experiments, including figures and tables, are saved in the `results` directory. Key findings include:

- **LBF significantly reduces memory usage** compared to standard BF while maintaining search accuracy.
- **Using DeepSMILES as a feature representation** enhances the performance of LBF.

## Figures

### Figure 1: PFAS and Non-PFAS Structures

*Figure 1: Chemical structures of PFAS and non-PFAS compounds.*

### Figure 2: Architecture Comparison between BF and LBF

*Figure 2: Comparison of the architecture between traditional Bloom Filter and Learned Bloom Filter.*

### Figure 3: FPR vs. Memory Usage

*Figure 3: Relationship between False Positive Rate (FPR) and memory usage for BF and LBF.*

### Figure 4: Effect of Feature Representation on LBF Performance

*Figure 4: Comparison of LBF performance using SMILES and DeepSMILES representations.*

## Citation

If you use this code or datasets in your research, please cite our paper:

```bibtex
@article{nishida2023efficient,
  title={Efficient Chemical Compounds Search Using Learned Bloom Filter},
  author={Nishida, Ken and Hayashi, Katsuhiko and Kamigaito, Hidetaka and Shindo, Hiroyuki},
  journal={Journal of Chemical Informatics},
  year={2023},
  volume={XX},
  number={X},
  pages={XX--XX}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

We would like to thank all contributors and the community for their support.

## Contact

For any questions or inquiries, please contact:

- **Ken Nishida**: [ken.nishida@example.com](mailto:ken.nishida@example.com)

**Note**: Please ensure to replace placeholders like `link-to-your-paper.pdf`, `ken.nishida@example.com`, and any other placeholders with actual information relevant to your repository.

## References

1. Kraska et al., "The Case for Learned Index Structures", 2018.
2. Medina et al., "Bloom Filter Molecules: Fast Chemical Similarity Search Using Bloom Filters", 2023.
3. Weininger, D., "SMILES, a chemical language and information system. 1. Introduction to methodology and encoding rules", 1988.
4. O'Boyle, N.M., "Towards a Universal SMILES Representation - A Standard Method to Generate Canonical SMILES Based on the InChI", 2012.

## Supplementary Information

### Equations

#### Equation 1: Insertion into Bloom Filter

\[
B[h_{i}(x)] = 1, \quad orall i = 1, 2, ..., k
\]

#### Equation 2: Optimal Bit Array Length

\[
m = -\frac{n \ln \epsilon}{(\ln 2)^2}
\]

#### Equation 3: Optimal Number of Hash Functions

\[
k = \frac{m}{n} \ln 2
\]

#### Equation 4: Binary Cross Entropy Loss

\[
\text{BCE Loss} = -\frac{1}{N} \sum_{i=1}^{N} \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]
\]

#### Equation 5: False Positive Rate

\[
\text{FPR} = \frac{\text{FP}}{\text{FP} + \text{TN}}
\]

#### Equation 6: Total Memory Usage of LBF

\[
S_{LBF} = S_{RNN} + S_{BF}
\]

### Datasets Description

- **PFAS Dataset**: Contains SMILES representations of per- and polyfluoroalkyl substances, known for their persistence in the environment.
- **PCBA Dataset**: PubChem BioAssay dataset containing biological activity data for various molecules.

---

Please feel free to explore the repository and utilize the resources provided. Contributions and feedback are welcome!

