# Molecular Property Prediction Challenge

**Contributors:**  
- Ridham Patel  
- Parthiv Patel  

---

## Challenge Overview

Welcome to the **Molecular Property Prediction Challenge** — a chemistry-meets-machine learning competition where the goal is to **predict molecular dipole moments** using **3D molecular structures** provided in XYZ format.

Dipole moments are crucial molecular properties with applications in **solvation**, **reactivity**, **spectroscopy**, and **materials design**. Accurately predicting these values from raw 3D structures can significantly accelerate progress in **computational chemistry** and **materials science**.

---

## Why Graph-Based Architectures?

Molecules are inherently graph-structured data — atoms as nodes and bonds (or interatomic relationships) as edges. Traditional ML methods fail to capture this relational structure effectively.

**Advantages of using Graph Neural Networks (GNNs) & Graph Transformers:**
- Leverage both **topological** (bond connectivity) and **geometric** (3D spatial) information.
- Provide **permutation invariance** and **rotational equivariance**, crucial for molecular data.
- Handle variable-sized input (different number of atoms per molecule).
- Allow rich feature propagation via **message passing** or **attention mechanisms**.

These architectures offer a natural and powerful way to learn molecular representations that are well-suited for property prediction tasks.

---

## Goal

Your objective is to **predict the dipole moment** of a set of small organic molecules, given only their **3D atomic structures**.

This is not your typical clean tabular dataset — expect raw, scientific-format data that demands serious preprocessing. You'll need to:

- Parse `.xyz` files to extract atomic symbols and 3D coordinates  
- Extract meaningful features (geometric, atomic, or descriptor-based)  
- Decide on the molecular representation (e.g., fingerprints, SOAP descriptors, or graph embeddings)  
- Clean and transform the data into a model-ready format  

---

## Our Approach

We tackled this challenge using **Graph Neural Networks (GNNs)** and later enhanced our models using a **Graph Transformer** architecture inspired by **Uni-Mol**, which incorporates:

- **3D spatial positional encodings**  
- **Attention-based message passing**  
- Ability to model both local and global molecular contexts  

This hybrid approach allowed us to exploit both the **chemical connectivity** and **3D geometry** of molecules, leading to more accurate dipole moment predictions.

---

## Future Work

- Incorporating quantum chemical descriptors (e.g., Mulliken charges, HOMO-LUMO gap)  
- Exploring equivariant models like **SE(3)-Transformers**  
- Scaling to larger molecules and datasets  

---

## Tech Stack

- Python, PyTorch, PyTorch Geometric  
- RDKit for molecular parsing and featurization  
- DScribe for descriptor generation (SOAP, ACSF)  
- ASE for reading XYZ structures  
