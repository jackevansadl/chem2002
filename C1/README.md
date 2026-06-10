***
# C1: Foundations of Computational Chemistry

> **Run on Google Colab (no installation required):**
> | Notebook | Open in Colab |
> |---|---|
> | `01_SystemSetup.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C1/01_SystemSetup.ipynb) |
> | `02_RunMD.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C1/02_RunMD.ipynb) |
> | `03-Analysis.ipynb` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jackevansadl/chem2002/blob/main/C1/03-Analysis.ipynb) |

Welcome to the first computational chemistry workshop for CHEM 2002 Physical and Inorganic Chemistry 2! Ever wondered what molecules actually do in a liquid? This session is designed to make the abstract principles of thermodynamics tangible by simulating molecular motion right on your computer. You'll build a system of argon atoms, watch them move, and calculate a real thermodynamic property from their behavior.

***
#### **🎯 Learning Objectives**
By the end of this workshop, you'll be able to:
* Use computational tools to visualize and analyze molecular structures.
* Integrate digital tools into your chemical problem-solving workflow.
* Set up and run a basic molecular dynamics simulation.
* Calculate a thermodynamic property ($C_v$) from simulation data.
* Create professional-quality figures to communicate scientific data.

***
#### **📝 Pre-Practical Preparation**

Before the workshop, complete the **C1 Pre-Practical Readiness Check** on Canvas — a short, auto-graded warm-up (not a test). It runs *before* the related lectures, so every question carries the background you need, and all of these ideas are taught from scratch inside the notebooks. It covers:

* **System, surroundings & state variables** — what we study versus everything else.
* **Open / closed / isolated systems** — classifying our thermostatted box.
* **Heat capacity** — $C_v$ versus $C_p$, and why our fixed-volume box gives $C_v$.
* **Temperature & kinetic energy** — the equipartition idea.
* **The Lennard-Jones potential** — long-range attraction ($r^{-6}$) and short-range repulsion ($r^{-12}$).

> 📋 The quiz is in [`canvas-quizzes/`](../canvas-quizzes/) (`C1_prepractical_quiz`) as an importable Canvas QTI package, with editable source.

***
#### **📓 Practical Materials**
This workshop is divided into three parts. Please complete the Jupyter Notebooks in the following order:

* **`01_SystemSetup.ipynb`**: Learn to build a 3D model of a molecule from a text string and construct the cubic simulation box of Argon atoms that will serve as our system.
* **`02_RunMD.ipynb`**: Add the laws of physics to our system using a force field, run a molecular dynamics simulation to model atomic motion, and check that the system reaches equilibrium.
* **`03-Analysis.ipynb`**: Analyze the data from your simulation to calculate the constant volume heat capacity (C_v) of argon and compare it to the experimental value.

Each notebook contains guided explanations, **🔧 hands-on exercises** (predict-then-check), and **💭 reflection** prompts, with **⏱️ time markers** on each section.

> **⚠️ Transferring files between Part 2 and Part 3:** Google Colab runs each notebook in its own session. At the **end of `02_RunMD.ipynb`** you must **download** the `md.log` and `md.traj` files it produces, and at the **start of `03-Analysis.ipynb`** **upload** them again. Both notebooks include a cell to do this.

***
##### **⏱️ Instructor Pacing Guide (~4-hour session)**
| Part | Notebook | Approx. time |
|---|---|---|
| 1 | `01_SystemSetup.ipynb` | ~50 min |
| 2 | `02_RunMD.ipynb` | ~80 min (incl. short thermostat experiments) |
| 3 | `03-Analysis.ipynb` | ~45 min |
| | Pre-practical + reporting write-up | ~45 min |

Core content runs in ~3 h; the hands-on exercises (Exercises 1.A, 2.A, 2.B, 3.A) and reflection prompts take it to ~4 h. All extra MD runs are deliberately short (≈2000 steps) to keep the session moving on a free Colab CPU runtime.

***
##### **💻 Additional Materials & Software**
The notebooks use Python with several key scientific libraries, all of which are pre-installed in the Google Colab environment:
* **Atomic Simulation Environment (ASE):** For setting up and running simulations.
* **NumPy & Matplotlib:** For numerical analysis and plotting.
* **py3Dmol:** For interactive 3D visualization of molecular structures within the notebook.
* **RDKit:** For generating and visualizing simple 2D molecular structures.

You are also encouraged to download Avogadro, a free, powerful molecular editor. It's a great tool for visualizing molecules and chemical data outside of a notebook.

***
#### **📋 Practical Reporting**
As you work through the notebooks, you will be prompted to answer several questions and generate data. Here is a summary of the tasks for your workbook.

1.  **From `01_SystemSetup.ipynb`:**
    * What is the SMILES string for ethanol?
    * Include the 2D image and a screenshot of the 3D structure of ethanol.
    * Report the final dimensions and volume of the argon simulation box and your calculated density.

2.  **From `02_RunMD.ipynb`:**
    * Modify the argon simulation box generation code to produce the correct density at 100 K and 40 bar.
    * From the Lennard-Jones potential plot, estimate the distance (r) of minimum potential energy and explain its physical meaning.
    * Describe what the potential represents at very short interatomic distances.
    * From the Temperature vs. Time plot, confirm if the system reached the target temperature of 100 K.
    * Estimate how long (in ps) it took for the system to equilibrate.
    * Comment on what might happen if you change the `friction` parameter.

3.  **From `03-Analysis.ipynb`:**
    * Provide a copy of your Total Energy vs. Time plot and use it to estimate the equilibration time.
    * Report your final calculated value for the constant volume heat capacity ($C_v$) in J K⁻¹ mol⁻¹.
    * Compare your result to the experimental value and compare to other literature simulations. Discuss **two** potential reasons for any difference.