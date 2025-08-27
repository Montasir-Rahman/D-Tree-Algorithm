# D-Tree: A New Association Rule Mining Technique

This repository contains the implementation of the **D-Tree (Dominant-Tree)** algorithm, a novel Association Rule Mining (ARM) technique designed to improve the relevance and accuracy of mined patterns from transactional databases.

Unlike traditional algorithms like Apriori or FP-Growth that focus primarily on mitigating time and space complexity, D-Tree prioritizes the generation of authentic, meaningful patterns, addressing the business need for more actionable insights.

## 💡 Key Features

The D-Tree algorithm introduces several innovative concepts to enhance the efficiency and relevance of association rule mining:

* **InitSet**: A unique method of grouping identical transactions to compress the dataset and reduce scanning time.
* **Dominant Node Hierarchy**: An innovative tree-building approach that prioritizes the most impactful items, leading to a more efficient tree structure and more meaningful rules.
* **Non-Repeated Values (NRV)**: A novel mechanism used to prioritize which nodes are inserted into the tree, further optimizing the construction process.
* **List of Node Links**: Incorporates the efficient "List of Node Link" data structure from the EFP-Growth algorithm to accelerate tree traversal.

## ⚙️ How It Works

The D-Tree algorithm follows a two-stage process:

1.  **Data Pre-processing**: The algorithm first scans the database to find the frequency of each item. It then groups identical transactions into a compact structure called an `InitSet`, which significantly reduces the data volume.
2.  **Tree Construction**: The D-Tree is built transaction by transaction from the `InitSet`. For each transaction, it identifies a **"Dominant Node"**—either an item already present in the tree as a child of the root or the item with the highest frequency. This node becomes the parent, and the remaining items are recursively added. Transactions with items of equal frequency are temporarily sent to a buffer to be processed later, ensuring an optimal tree structure.

This approach not only reduces database scans but also builds a more compact and efficient tree, resulting in the generation of more accurate and relevant association rules.

## 📊 Performance

As demonstrated in the research paper, the D-Tree algorithm was evaluated against Apriori, FP-Growth, and EFP-Growth using benchmark datasets. The results show that D-Tree consistently **outperforms** its counterparts.

* **Higher Accuracy, Sensitivity, and AUC**: D-Tree achieves significantly better scores on these key performance metrics, indicating more reliable and trustworthy results.
* **Fewer, More Relevant Rules**: It generates a smaller set of association rules, filtering out noise and focusing on the most significant patterns.
* **Superior Efficiency**: On datasets like *Zoo* and *Mushroom*, D-Tree demonstrates lower execution times and requires significantly less memory, showcasing its efficiency.

## 🚀 Getting Started

### Prerequisites

* Python 3.x
* pyfpgrowth
* scikit-learn

### Installation

1.  Clone the repository:
    ```
    git clone [https://github.com/your-username/dtree.git](https://github.com/Montasir-Rahman/D-Tree-Algorithm.git)
    ```
2.  Navigate to the project directory:
    ```
    cd D-Tree-Algorithm
    ```
