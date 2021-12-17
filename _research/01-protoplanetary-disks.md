---
title: "Protoplanetary Disks"
permalink: /research/protoplanetary-disks/
---
# Introduction
Trial-and-error experiments have dominated the discovery of new materials in the past. In the information age, tremendous efforts have been devoted to shifting this paradigm to rational strategies guided by virtual screening, which requires the development of new advanced modeling methods. To speed the discovery of new materials from computer modeling, our group has been focusing on two aspects of materials informatics (1) developing the accurate machine learning potentials and (2) construct the functional materials databases.

# Machine Learining Interatomic potentials
Atomistic simulations have been used routinely to model the physical behaviors of many complex systems. The accuracy of the simulations is highly dependent on the underlying potential energy surface (PES) of the system. In principle, MD simulations can be based on quantum-mechanical or classical force field methods. The ab initio MD (AIMD) simulations usually employ density functional theory (DFT) approximation, which can provide a reliable representation of the system but is be limited to only a few hundreds of atoms. On the other hand, the classical MD method can model large systems at long-time scale, but they are often inadequate to describe the quantitative properties of the system.

Recently, machine learning methods have been widely applied to resolve the dilemma in comprising between accuracy and cost. The machine learning interatomic potential (MLIAP) are trained by minimizing the cost function to attune the model to deliberately describe the ab initio data. The cost of atomistic simulation is orders of magnitude lower than the quantum mechanical simulation, allowing the system to be scaled up to about one million atoms.
{% include figure image_path="/assets/images/materials-informatics/MLIAP.jpeg" caption="**Figure 1.** Machine learning potentials compared to the traditional quantum mechanical simulation" %}

Since 2019, our group has been developing the _[PyXtal\_FF](/research/pyxtalff/)_ ---a package for generating machine learning potentials. The aim of PyXtal\_FF is to promote the application of atomistic simulations by providing several choices of structural descriptors and machine learning regressions in one platform. Based on the given choice of structural descriptors (including the atom-centered symmetry functions, embedded atom density, SO4 bispectrum, and smooth SO3 power spectrum), PyXtal\_FF can train the MLPs with either the generalized linear regression or neural networks model, by simultaneously minimizing the errors of energy/forces/stress tensors in comparison with the data from the ab-initio simulation. The trained MLP model from PyXtal\_FF is interfaced with the Atomic Simulation Environment (ASE) package, which allows different types of light-weight simulations such as geometry optimization, molecular dynamics simulation, and physical properties prediction. Finally, we will illustrate the performance of PyXtal\_FF by applying it to investigate several material systems, including bulk, surfaces and nanoparticles. 
{% include figure image_path="/assets/images/materials-informatics/pyxtal-ff.jpeg" caption="**Figure 2.** The current status of PyXtal\_FF (2020/08)" %}


## Relevant works
1. Yanxon H., Zagaceta D., Wood B.C., **Zhu Q.** (2020).
__[Neural Networks Potential from the Bispectrum Component: A Case Study on Crystalline Silicon](https://doi.org/10.1063/5.0014677)__. (Open Access: [PDF](https://arxiv.org/pdf/2001.00972.pdf))

1. Zagaceta D., Yanxon H., **Zhu Q.** (2020).
__[Spectral Neural Network Potentials for Binary Alloys](https://aip.scitation.org/doi/10.1063/5.0013208)__.
J. Appl. Phys., 128, 045113. (Open Access: [PDF](https://aip.scitation.org/doi/pdf/10.1063/5.0013208%40jap.2020.MLMD2020.issue-1))

1. Yanxon H., Zagaceta D., Tang B., Matteson D., Zhu Q. (2020).
__[PyXtal FF: a Python Library for Automated Force Field Generation](https://arxiv.org/abs/2007.13012)__. (Open Access: [PDF](https://arxiv.org/pdf/2007.13012.pdf))

# Computational Materials Database
In the past, the identification of new materials required labor-intensive efforts, which included raw materials synthesis and sample characterization. Considering the current size of materials data (~30,000 after the removal of duplicates and structures with partial occupation) in the Inorganic Crystal Structure Database (ICSD), it is impossible to investigate each compound by trial-and-error experiments. The high-throughput (HT) computational materials design, based on a search for target materials from a large database containing necessary thermodynamic and electronic properties for all available materials, has become popular in materials science in recent years. Our group is generally interested in combinning the advanced structure prediction techniques with the high-throughput screening to discover the materials with target functionalities. Specifically, our efforts are focusing on the electrides and topological phononic materials. 


{% include figure image_path="/assets/images/materials-informatics/tpmd.png" caption="**Figure 3.** The schematic flowchart of high throughput screening on
topological phonons. More details can be found at our _[online database](https://tpdb.physics.unlv.edu)_" %}

{% include figure image_path="/assets/images/materials-informatics/electride.jpg" caption="**Figure 4.** The efforts on searching for the electrides. _[Source](/assets/pdfs/papers/2019-matter.pdf)_" %}


## Relevant works
1. Li J-X, Liu J-X, Baronett S.A., Li R-H, Wang L., **Zhu Q.** and Chen X-Q (2020).
__[Computation and data driven discovery of topological phononic materials](https://arxiv.org/abs/2006.00705)__. (Open Access: [PDF](https://arxiv.org/pdf/2006.00705.pdf))

1. Qu J-Y, Zagaceta D., Zhang W-W, **Zhu Q.** (2020).
__[High dielectric ternary oxides from crystal structure prediction and high-throughput screening](https://www.nature.com/articles/s41597-020-0418-6)__.
Sci. Data, 7, 81. (Open Access: [PDF](https://www.nature.com/articles/s41597-020-0418-6.pdf))

1. **Zhu Q**, Frolov T, K. Choudhary (2019) 
__[Computational Discovery of Inorganic Electrides from an Automated Screening](https://www.cell.com/matter/fulltext/S2590-2385(19)30069-4)__.
Matter, 1. 1293-1303 ([PDF](/assets/pdfs/papers/2019-matter.pdf) [Preview](https://www.cell.com/matter/pdf/S2590-2385(19)30282-6.pdf))

1. Zhu S-C, Wang L, Qu, J-Y, Wang, J-J, Frolov T, Chen X-Q and **Zhu, Q**. (2019) 
__[Computational Design of Flexible Electrides with Non-trivial Band Topology](https://journals.aps.org/prmaterials/abstract/10.1103/PhysRevMaterials.3.024205)__
Phys. Rev. Materials, 3, 024205 ([pdf](/assets/pdfs/papers/2019-PRM.pdf))

1. Wang J-J, **Zhu, Q**, Wang Z-H, Hosono H. (2019)
__[Ternary Inorganic Electrides with mixed bonding](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.99.064104)__
Phys. Rev. B, 99, 064104 ([pdf](/assets/pdfs/papers/2019-PRB.pdf))

1. Qu J-Y, Zhu S-C, Zhang W-W, and **Zhu, Q**. (2019) 
__[Electrides with Dinitrogen Ligands](https://pubs.acs.org/doi/10.1021/acsami.8b18676)__
ACS Appl. Mater. Interfaces, 11, 5256-5263 ([pdf](/assets/pdfs/papers/2019-AMI.pdf))


