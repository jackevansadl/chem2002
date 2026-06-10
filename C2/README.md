***
# C2: Chemical Bonding and Molecular Orbitals

Welcome to the second computational chemistry workshop for CHEM 2002 Physical and Inorganic Chemistry 2! In C1 you treated atoms as simple spheres bouncing around a box. Now we go *inside* the atom to answer a deeper question: **why do atoms bond at all, and why do the resulting molecules have the colours, shapes and magnetic properties that they do?** The answer is **Molecular Orbital (MO) theory**, and in this workshop you'll use real quantum-chemistry software to see molecular orbitals in 3D.

> **Run on Google Colab (no installation required):**
> | Notebook | Open in Colab |
> |---|---|
> | `01_Atoms_to_Orbitals.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C2/01_Atoms_to_Orbitals.ipynb) |
> | `02_MO_Diagrams_N2_O2.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C2/02_MO_Diagrams_N2_O2.ipynb) |
> | `03_Crystal_Field_TM_Complexes.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C2/03_Crystal_Field_TM_Complexes.ipynb) |

***
#### **🎯 Learning Objectives**
By the end of this workshop, you'll be able to:
* Explain how atomic orbitals combine to form **bonding** and **antibonding** molecular orbitals.
* Use computational tools to **visualise molecular orbitals** in 3D.
* Construct **MO energy-level diagrams** and determine **bond order**.
* Explain the **magnetism** of molecules such as O$_2$ using MO theory, where Lewis structures fail.
* Apply **crystal field theory** to predict the **colour** and **magnetism** of transition-metal complexes.

***
#### **📝 Pre-Practical Preparation**

Before the workshop, complete the **C2 Pre-Practical Readiness Check** on Canvas — a short, auto-graded warm-up (not a test). It runs *before* the related lectures, so every question carries the background you need, and all of these ideas are taught from scratch inside the notebooks. It covers:

* **Bonding vs antibonding orbitals** — and what a **node** is.
* **Bond order** — and what it says about bond strength and length.
* **Paramagnetic vs diamagnetic** — unpaired versus paired electrons.
* **d orbitals in an octahedral field** — the $t_{2g}$ and $e_g$ sets.
* **High- vs low-spin** — the contest between $\Delta_o$ and the pairing energy.

> 📋 The quiz is in [`canvas-quizzes/`](../canvas-quizzes/) (`C2_prepractical_quiz`) as an importable Canvas QTI package, with editable source.

***
#### **📓 Practical Materials**
This workshop is divided into three parts. Please complete the Jupyter Notebooks in the following order:

* **`01_Atoms_to_Orbitals.ipynb`**: Visualise atomic orbitals, then combine two hydrogen 1*s* orbitals into a bonding and an antibonding molecular orbital. See how the picture changes for a polar bond (CO).
* **`02_MO_Diagrams_N2_O2.ipynb`**: Build molecular-orbital energy-level diagrams for N$_2$ and O$_2$, read off the bond order, and explain why O$_2$ is magnetic — something Lewis structures get wrong.
* **`03_Crystal_Field_TM_Complexes.ipynb`**: Apply these ideas to transition-metal complexes. See how the *d* orbitals split in an octahedral field, and how that splitting controls colour (high/low spin) and magnetism.

Each notebook contains guided explanations, **🔧 hands-on exercises** (predict-then-check), and **💭 reflection** prompts, with **⏱️ time markers** on each section.

> **📚 A note on theory:** notebook 3 uses **Crystal Field Theory** (ligands treated as point charges) as an accessible first model. In your CHEM 2002 lectures this is extended to **Ligand Field Theory**, which also includes the covalent overlap between metal and ligand orbitals — the same $t_{2g}/e_g$ splitting, explained more fully.

***
##### **⏱️ Instructor Pacing Guide (~4-hour session)**
| Part | Notebook | Approx. time |
|---|---|---|
| 1 | `01_Atoms_to_Orbitals.ipynb` | ~60 min |
| 2 | `02_MO_Diagrams_N2_O2.ipynb` | ~70 min |
| 3 | `03_Crystal_Field_TM_Complexes.ipynb` | ~75 min (+ optional ~5 min DFT run) |
| | Pre-practical + reporting write-up | ~35 min |

Core content runs in ~3.5 h; the hands-on exercises and reflection prompts fill the ~4 h. Every calculation (apart from the clearly-labelled optional DFT bonus) runs in well under a second on a free Colab CPU runtime.

***
##### **💻 Additional Materials & Software**
The notebooks use Python with several scientific libraries, all of which install automatically in the first cell on Google Colab:
* **PySCF:** An open-source quantum-chemistry program used to calculate molecular orbitals.
* **py3Dmol:** For interactive 3D visualisation of orbitals within the notebook.
* **NumPy & Matplotlib:** For numerical analysis and drawing MO/splitting diagrams.
* **RDKit & ASE:** For building and handling molecular structures.

There is also an **optional bonus** in notebook 1 that lets you try **Microsoft Skala** (2025), a deep-learning DFT functional that plugs into PySCF — purely for interest, not required for any task.

***
#### **📋 Practical Reporting**
As you work through the notebooks, you will be prompted to answer several questions. Here is a summary of the tasks for your workbook.

1.  **From `01_Atoms_to_Orbitals.ipynb`:**
    * Calculate **He$_2$**, visualise its bonding ($\sigma$) and antibonding ($\sigma^*$) orbitals, and work out its **bond order**.
    * Explain why **He$_2$ is not a stable molecule**.

2.  **From `02_MO_Diagrams_N2_O2.ipynb`:**
    * Complete the table of **bond order** and **magnetism** for N$_2$, O$_2$, O$_2^{+}$ and F$_2$.
    * Explain how the bond order of **O$_2^{+}$** compares to O$_2$, and what that predicts about its bond length.

3.  **From `03_Crystal_Field_TM_Complexes.ipynb`:**
    * For an **Fe(III) (d$^5$)** complex, find the number of **unpaired electrons** for a weak-field and a strong-field ligand, and explain the difference using high-/low-spin.
    * Use the colour tool to **predict the colour** of [Ni(H$_2$O)$_6$]$^{2+}$ ($\Delta_o = 17400$ cm$^{-1}$).
    * Explain why strong-field ligands give **larger** $\Delta_o$ and absorb at **shorter** wavelengths.
