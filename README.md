# cross-lingual-cost
This repo includes benchmarks and corpora presented in the paper ["The Cross-Lingual Cost: Retrieval Biases in RAG over Arabic-English Corpora"](https://arxiv.org/abs/2507.07543) by Amiraz et al., accepted to ArabicNLP 2025.

## Benchmark Details
Both benchmarks are derived from public websites that contain parallel content in English and Arabic. The first benchmark, Legal, is based on the [UAE Legislation website](https://uaelegislation.gov.ae), which contains 390 laws, with each law described in separate documents in English and Arabic. The second benchmark, Travel, is based on the [UAE Ministry of Foreign Affairs website](https://www.mofa.gov.ae/ar-ae/travel-updates), which offers travel-related information for multiple countries, such as visa requirements and embassy contacts. For each country, the information is presented in two parallel documents, one per language.

In order to build a corpus for each of these two use cases, we assigned a document language to each document uniformly at random during corpus construction, ensuring that every document appears in exactly one language within the corpus.
The resulting Legal corpus includes roughly 1.5M  words, while the Travel corpus contains around 150K words.
After building and indexing this bilingual corpus, we proceeded to create the benchmark. We used DataMorgana ([Filice et al., 2025](https://aclanthology.org/2025.acl-industry.33/)), a synthetic question–answer generation tool, to create query–answer pairs per document, ensuring that each question could be answered using that document alone. The language of each query–answer pair (the user language) is also selected uniformly at random and independently of the document language, resulting in a benchmark that supports systematic evaluation across all language combinations, and allows to identify the source of bias.
The final benchmarks include around 1.3K question–answer pairs for Legal and 2K for Travel. Further details may be found in the paper.

## Citation
If you use this dataset, please cite our paper:

```bibtex
@article{amiraz2025crosslingual,
  title   = {The Cross-Lingual Cost: Retrieval Biases in RAG over Arabic-English Corpora},
  author  = {Amiraz, Chen and Fyodorov, Yaroslav and Haramaty, Elad and Karnin, Zohar and Lewin-Eytan, Liane},
  journal = {arXiv preprint arXiv:2507.07543},
  year    = {2025},
  note    = {Accepted at ArabicNLP 2025}
}