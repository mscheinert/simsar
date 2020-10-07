# Simulation Meta Data

It is the **meta data** that allows objects, like data sets and model setups to be findable by both humans and machines. They are therefore an essential part of a simulation package that is going to be published or shared with others for further development.

However, the compilation of the meta data can be a bold venture: on the one hand it is extremely useful to have every tiny detail to look for. On the other hand the user has to provide all the information in the first place which costs time, especially if the meta data requires a lots of tweaking and transformation. Which rises immediately the question 

"*What is the adequate set of meta data that supports effective search processes while  keeping the effort at a low level?*"

Before answering this question, we need to know the overall extent and the major components of the sharable object, the "Simulation Package".

## The Simulation Package

The SImulation Package comprises the aforementioned components:

1. The source code (code base and user modifications)

2. The setting and environment  for the build process (model conponents, macros and compiler choices)

3. The run-time environment for a specific simulation (parameters and input)

4. Control output for evaluation



![](img/simsar_SimulationPackage.png){: .center .imgshadow}

### 1. Source Code

The **code base**, a simulation is build from, must be unequivocally identifiable, i.e. the code must be version controlled and the exact revision must be known. NEMO uses *Subversion* as a version control system. Changes are tracked on the server globally and each modification (commit) is associated with a globel changeset/revision number. This can lead to situations where two checkouts represent the exact same code although the revision numbers are different. But together with the directory structure for the different development and release branches the code base for a specific simulation can be sufficently characterized and **referenced**.

**Code modifications** and extensions on top for a simulation must be be tracked and controlled by the user. Refering to a private repository (svn or git) however might not be sufficient and implicates some risk regarding mid- and long-term documentation. This part of the code should be therefore **included in the package**.

### 2. Build Environment

Beside the code base and the code modifications by the user, the **build environment** is another essential module in order to sustain a reproducible  simulation development. It must be documented, which components of the code have been included (**model components**) and whether and how macro definitions (**CPP Keys**) for masking the code were involved. Furthermore, the **manufacturer** and the **version** of the **compiler** itself as well as the **options** and **arguments** of the compiler **command** must be put on record.

### 3. Run-time Environment

Even with the same executable, complete different simulations can be achieved by slightly changing only a few parameters, boundary conditions or the initial state. While the run-time parameters (FORTRAN namelists) can be easily documented (they could be even transferred to some Database), 

### 4. Evaluation