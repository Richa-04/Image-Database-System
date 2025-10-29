# 🖼️ Image Database System

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Latest-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-Academic-lightgrey?style=for-the-badge)](#)

## Overview

A powerful image classification and retrieval system using advanced feature descriptors, dimensionality reduction, and multiple indexing techniques.

---

## 📋 Table of Contents

- [System Components](#-system-components)
- [Quick Start](#-quick-start)
- [Tasks Overview](#-tasks-overview)
- [Detailed Usage](#-detailed-usage)

---

## 🔧 System Components

### Feature Descriptors
The system supports three feature extraction methods:
- **`cm`** - Color Moments
- **`elbp`** - Extended Local Binary Patterns
- **`hog`** - Histogram of Oriented Gradients

### Image Types
Compatible with various image transformations:
```
cc | con | emboss | jitter | neg | noise1 | noise2 | original | poster | rot | smooth | stipple
```
> 💡 **Note:** Image type names are dataset-dependent and may vary.

### Dataset Parameters
- **Subjects:** 1-40 (string format)
- **Sample IDs:** 1-10 (string format)
- **Dimensionality Reduction:** SVD (Singular Value Decomposition)

### Classification Methods
- **`decision_tree`** - Decision Tree Classifier
- **`ppr`** - Personalized PageRank
- **`svm`** - Support Vector Machine

---

## 🚀 Quick Start

### Prerequisites
```bash
pip install -r requirements.txt
```

### Basic Example
```bash
python task1.py -fp 'train_set/500' -f cm -k 10 -qf 'test_set/100' -c ppr
```

---

## 📊 Tasks Overview

| Task | Purpose | Key Features |
|------|---------|--------------|
| **Task 1-3** | Image Classification | Train classifier with latent semantics |
| **Task 4** | LSH Indexing | Locality-Sensitive Hashing with multiple layers |
| **Task 5** | VA-File Indexing | Vector Approximation with bit quantization |
| **Task 6-8** | Query & Retrieval | Interactive search and retrieval operations |

---

## 📖 Detailed Usage

### Task 1: Classification Pipeline (Type-Based)

Train and evaluate classifiers using latent semantics derived from image features.

**Syntax:**
```bash
python task1.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
```

**Parameters:**
- `-fp` : Training dataset folder path
- `-f` : Feature descriptor (`cm`, `elbp`, `hog`)
- `-k` : Number of latent semantic dimensions
- `-qf` : Query/test images folder path
- `-c` : Classifier type (`decision_tree`, `ppr`, `svm`)

**Example:**
```bash
python task1.py -fp 'train_set/500' -f cm -k 10 -qf 'test_set/100' -c ppr
```

---

### Task 2: Classification Pipeline (Subject-Based)

Similar to Task 1, optimized for subject-based classification.

**Syntax:**
```bash
python task2.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
```

**Example:**
```bash
python task2.py -fp 'train_set/500' -f elbp -k 15 -qf 'test_set/100' -c svm
```

---

### Task 3: Enhanced Classification

Advanced classification with improved feature processing.

**Syntax:**
```bash
python task3.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -qf [query_images_folder_path] -c [classifier]
```

**Example:**
```bash
python task3.py -fp 'train_set/500' -f hog -k 20 -qf 'test_set/100' -c decision_tree
```

---

### Task 4: LSH Index Creation

Build Locality-Sensitive Hashing index for efficient similarity search.

**Syntax:**
```bash
python task4.py -fp [folder_path] -f [feature_descriptor] -l [number_of_layers] -k [latent_semantics_num] -kh [hash_functions_per_layer]
```

**Parameters:**
- `-fp` : Dataset folder path (use `"all"` for entire dataset)
- `-f` : Feature descriptor
- `-l` : Number of hash table layers
- `-k` : Latent semantic dimensions (use `"all"` for no reduction)
- `-kh` : Number of hash functions per layer

**Example:**
```bash
python task4.py -fp "all" -f elbp -l 5 -k "all" -kh 10
```

---

### Task 5: VA-File Index Creation

Create Vector Approximation file index for fast approximate search.

**Syntax:**
```bash
python task5.py -fp [folder_path] -f [feature_descriptor] -k [latent_semantics_num] -b [bits_per_dimension]
```

**Parameters:**
- `-fp` : Dataset size or folder path
- `-f` : Feature descriptor
- `-k` : Latent semantic dimensions (use `-1` for all dimensions)
- `-b` : Number of bits per dimension for quantization

**Example:**
```bash
python task5.py -fp '4000' -f cm -k -1 -b 3
```

---

### Tasks 6, 7, 8: Query & Retrieval

Interactive system for image querying and retrieval using created indices.

**Syntax:**
```bash
python task6_7_8.py
```

**Interactive Inputs:**
```
Index file: index_lsh_cm_-1_5_9.json
Query image: 500/image-cc-1-1.png
```

**Features:**
- Task 6: LSH-based similarity search
- Task 7: VA-File based search
- Task 8: Hybrid retrieval methods

---

## 📝 Notes

- All folder paths can be relative or absolute
- String parameters should be enclosed in quotes
- Use `"all"` for maximum feature dimensions when applicable
- Index files are saved with descriptive names including all parameters

---

**Happy Image Searching! 🔍✨**
