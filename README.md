# 🧬 Network Analysis of Protein-Protein Interactions (PPIs) in Non-Small Cell Lung Cancer (NSCLC)

### 🔬 By: Lakshmi Sindhu Pulugundla  
🎓 CS-579: Online Social Network Analysis  

---

## 📌 Introduction

Lung cancer is among the most prevalent and deadly cancers globally, with **Non-Small Cell Lung Cancer (NSCLC)** accounting for nearly **85%** of all cases. This project utilizes **network science and bioinformatics** to analyze **protein-protein interaction (PPI)** networks in NSCLC using data from the **STRING database**.

Our primary goal is to identify **functionally significant and therapeutically relevant proteins** using **centrality-based network analysis**. These key nodes may serve as potential **drug targets** or help **uncover critical biological mechanisms** in cancer progression.

---

## 🎯 Objectives

1. **Construct a detailed PPI network** specific to NSCLC using STRING data.
2. **Identify key proteins and pathways** using centrality measures.
3. **Analyze network dynamics** and determine structural vulnerabilities and therapeutic opportunities.

🔗 **Project Notebook**: [CSE-579 Final Project - Colab](https://colab.research.google.com/drive/19fNUyafFIGv9z_yTEVXwK7kYBMv7iw3l?usp=sharing)

---

## 🧾 Datasets Used

Extracted from [STRING-db](https://string-db.org):

- `string_interactions.tsv` – Protein interaction scores (combined and individual).
- `string_protein_annotations.tsv` – Alternative protein names.
- `string_functional_annotations.tsv` – Functional roles and biological pathways.
- `string_node_degrees.tsv` – Protein connectivity counts in the PPI network.

### 🔍 Data Preparation

- Mapped inconsistent protein IDs across datasets.
- Merged annotations and degrees into the interaction dataset.
- Validated with:
  - Statistical checks
  - Manual cross-verification
  - Use of KEGG pathway references

---

## 🧪 Methodology

### 1. Data Acquisition & Cleaning
- Standardized column names.
- Dropped irrelevant columns.
- Focused on proteins related to **NSCLC pathways**.

### 2. Merging & Validation
- Aligned and integrated datasets using unique protein identifiers.
- Ensured structural integrity of the merged data through visual and statistical validation.

### 3. Exploratory Data Analysis
- **Histograms & Boxplots** of interaction scores and node degrees.
- **Pair Plot** to uncover relationships between biological features.

### 4. Network Construction
- Built PPI network using NetworkX:
  - **Nodes**: Proteins
  - **Edges**: Interactions weighted by `combined_score`.
- Applied spring layout for visualization.

### 5. Centrality Analysis

Computed:

- **Degree Centrality** – High: TP53, AKT1  
- **Closeness Centrality** – High: TP53, EGFR  
- **Betweenness Centrality** – High: TP53, RXRA  
- **Eigenvector Centrality** – High: KRAS, AKT1

### 6. Visualization

- Used node **size** and **color** to represent centrality.
- **Edge width** and **intensity** indicated interaction strength.
- Subnetworks around top proteins were rendered for clarity.

---

## 📊 Key Visualizations

- 📈 **Histograms** of Node Degrees  
- 📊 **Boxplots** of Interaction Scores  
- 🔍 **Pair Plot** for Feature Relationships  
- 🕸 **Full Network Visualization**  
- 🎯 **Subgraph: Degree Centrality** Highlights

---

## 📌 Key Findings

| Protein | Roles & Insights |
|--------|-------------------|
| **TP53** | Tumor suppressor, most central in all measures |
| **AKT1** | Regulates survival and apoptosis |
| **KRAS** | Mutated in NSCLC, key in signal transduction |
| **EGFR** | Growth receptor, known drug target |
| **STAT3**, **PIK3CA**, **NRAS**, **HRAS** | Involved in critical NSCLC pathways |

### 🔑 Summary:

- Central proteins are **hubs**, **bridges**, or **influencers** in the NSCLC network.
- Potential **drug targets** and **biomarkers** identified.
- The **hub-and-spoke** structure makes the network vulnerable to disruptions at central nodes.

---

## 🧠 Reflections & Learnings

> “This project has deepened my understanding of how computational tools can unravel the complexity of cancer biology. I learned to value meticulous data preparation and the power of graph theory in biomedical discovery.”

If repeated:
- I'd implement **more robust data validation**.
- Explore **machine learning** for predicting protein function.
- Allocate more time to **subgraph analysis** of key nodes.

---

## 🔭 Future Work

1. **Dynamic Network Simulations** – To assess drug impact on network structure.
2. **Integration with Genomic Data** – Toward personalized network models.
3. **Experimental Validation** – To confirm computational findings.
4. **Focused Subgraph Exploration** – For top 10 proteins by centrality.
5. **Targeted Therapy Design** – Based on identified structural vulnerabilities.

---

## 🔗 References

- STRING Database: [string-db.org](https://string-db.org)
- KEGG Pathways: [NSCLC – map05223](https://www.genome.jp/entry/map05223)
- Clinical Literature:
  - [KRAS Mutations – Clinical Lung Cancer](https://www.clinical-lung-cancer.com/article/S1525-7304(11)70275-3/abstract)
  - [Molecular Pathology of NSCLC – Karger](https://karger.com/res/article-abstract/72/3/313/294494)

---

## 💾 Output File

```bash
nslc_interactions.csv
