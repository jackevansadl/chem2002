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

These are **warm-up questions, not a test** — this workshop runs *before* much of the related lecture material, so each question below comes with the background you need. Have a go at them; the notebooks then let you explore each idea hands-on, and you'll meet them again, in more depth, in lectures. (The full theory is also taught inside the notebooks themselves.)

1.  **System, surroundings and state variables.** In thermodynamics we split the universe into the **system** (the part we study) and the **surroundings** (everything else). A **state variable** (or *state function*) is a property that describes the system's current condition — like its temperature, volume or energy — regardless of how it got there.
    *Question:* For our simulation of argon atoms in a box, what is the **system** and what is the **surroundings**? Name one **state variable** we could monitor as it runs.

2.  **Open, closed or isolated.** A system is **open** if it can exchange both matter and energy with its surroundings, **closed** if it exchanges energy but not matter, and **isolated** if it exchanges neither.
    *Question:* Our box has a fixed number of atoms but uses a *thermostat* that lets energy flow to and from a virtual "heat bath". Is this system open, closed, or isolated? Briefly justify your choice.

3.  **Heat capacity.** Heat capacity measures how much energy you must add to raise a substance's temperature by 1 K — a substance with a *high* heat capacity needs a lot of energy for a small temperature rise. It is measured either at constant volume ($C_v$) or constant pressure ($C_p$); they differ because at constant pressure some added energy also does work by expanding the substance.
    *Question:* Our box is **sealed with fixed dimensions** (constant volume). Which of $C_v$ or $C_p$ will we be calculating, and why?

4.  **Temperature and motion.** Temperature is really a measure of the **average kinetic energy** of the atoms — hotter means they move faster on average. (The principle that pins this down quantitatively, the *equipartition theorem*, is explained in notebook 2 and developed in lectures.)
    *Question:* In one sentence, describe the link between how fast the argon atoms move and the temperature you would measure.

5.  **The Lennard-Jones potential.** Atoms attract each other weakly at long range (van der Waals forces, the $r^{-6}$ term) but repel very strongly when pushed too close together, because their electron clouds overlap (the $r^{-12}$ term). The Lennard-Jones potential combines these into one simple equation for the energy between two atoms.
    *Question:* In your own words, what does each of the two terms ($r^{-6}$ attraction and $r^{-12}$ repulsion) represent physically?

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