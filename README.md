# 🧬 MD_analysis_oligomers

**Analysis of molecular dynamics (MD) simulations of RNA oligomers**

This repository provides data and analysis tools for studying the structural dynamics of RNA oligomers, specifically:

- **distances between nucleobases**, computed via their **C5 carbon atoms** (within the base rings)
- **Hydrogen bonds** between bases, detected throughout the MD trajectories

The project includes preprocessed structural data and a ready-to-run analysis notebook.  

---

## 📁 Repository structure

```
MD_analysis_oligomers/
├── DATA_structures/
│ ├── molname_distances_i.npy # C5–C5 distances for subtrajectory i of oligomer 'molname'
│ ├── molname_Hbonds_i.npy # Hydrogen bonds for subtrajectory i
│ ├── reference_test_molname.pdb # Reference PDB structure of each oligomer
│ └── n_frames.pickle # Number of frames per subtrajectory
│
├── my_notebooks/
│ ├── importdata.ipynb # Preprocesses raw MD output from remote university storage and uploads to Zenodo
│ ├── importdata_structure.ipynb # Preprocesses raw MD output from remote university storage and uploads to DATA_structures
│ └── MD_analysis_complete.ipynb # Full-featured exploratory notebook (not standalone)
│
├── MD_analysis.ipynb # Standalone analysis notebook using data from DATA_structures
└── README.md # This file
```

## 🧪 Project overview

This project supports structural analysis of RNA oligomers based on MD simulations.  
Key observables include:

- **C5–C5 distances**: Used to quantify base–base spatial relationships
- **Hydrogen bonds**: Computed using geometric criteria between donor/acceptor atoms

These quantities have been computed from raw MD data on remote university storage as described in [`importdata_structure.ipynb`](my_notebooks/importdata_structure.ipynb)

---

## ⚡ Quick start: minimal analysis (from DATA_structures)

To explore the results with data only from DATA_structures (inter-residue distances and hydrogen bonds):

  - Run the analysis: [`MD_analysis.ipynb`](MD_analysis.ipynb)

     Self-contained analysis using data in [`DATA_structures`](DATA_structures/)

> ✅ Does **not require raw MD outputs**  
> ✅ Recommended for most users

---

## 🧬 Full workflow (for reference only)

- [`importdata.ipynb`](my_notebooks/importdata.ipynb):  
  Used to extract raw MD output from a **remote university network storage** and upload the data to Zenodo. Not runnable without access to that network.

- [`importdata_structure.ipynb`](my_notebooks/importdata_structure.ipynb):  
  Used to extract raw MD output from a **remote university network storage**, compute C5 distances and Hydrogen bond files from raw trajectories, and upload these data to [`DATA_structures`](DATA_structures/). Not runnable without access to that network.

- [`MD_analysis_complete.ipynb`](my_notebooks/MD_analysis_complete.ipynb):  
  A detailed, exploratory version of the analysis.

---

## 📄 Data description: `DATA_structures/`

This directory contains all you need for structural analysis in [`MD_analysis.ipynb`](MD_analysis.ipynb):

- `molname_distances_i.npy`  
  → Numpy array of pairwise **C5–C5 distances** between nucleobases for subtrajectory `i` of oligomer `molname`

- `molname_Hbonds_i.npy`  
  → Numpy array of hydrogen bonds between nucleobases over time for the same subtrajectory

- `reference_test_molname.pdb`  
  → Reference PDB structure for each RNA oligomer

- `n_frames.pickle`  
  → Dictionary of frame counts per trajectory segment

---

Further data (beyond inter-residue distances and hydrogen bonds) are publicly available on Zenodo.https://zenodo.org/records/14956459. To download data from it you can also look at https://github.com/bussilab/MDRefine (first cells in tutorial to download data, notebooks \texttt{load\_data\_oligomers} and \texttt{load\_data\_alchemical} to see how data have been loaded on Zenodo).

## 📦 Dependencies

The main notebook [`MD_analysis.ipynb`](MD_analysis.ipynb) requires the following Python libraries:

```
python
os
pandas
pickle
numpy
matplotlib
sklearn
MDAnalysis
```

You can install them via:

`pip install pandas numpy matplotlib scikit-learn MDAnalysis`

## 📚 Scientific context

This project enables systematic analysis of RNA conformational behavior from MD simulations.  
The data provide insights into:

- **base pairing and stacking** through C5–C5 distances  
- **stability and dynamics** of inter-base hydrogen bonds

If you use this dataset or code in your research, please cite the associated Zenodo record.

📦 **Zenodo dataset**: [https://zenodo.org/records/14956459](https://zenodo.org/records/14956459)  
📖 **code to load data**: [https://github.com/bussilab/MDRefine](https://github.com/bussilab/MDRefine)

---

## 🙋‍♀️ Questions or feedback?

Feel free to:

- 📂 [Open an issue](https://github.com/IvanGilardoni/MD_analysis_oligomers/issues)
- 📧 Contact the author: `igilardo@sissa.it`

