---
title: "Planet Formation"
permalink: /research/planet-formation/
---
# Introduction
The similarities and differences among structures of polymorphic molecular compounds have generated considerable commentary. If one can predict the crystal structures for a given molecule, it would help determine the likelihood that different forms exist, and suggest as yet unseen polymorphs of currently known structures. 


# Crystal Structure Prediction based EA
Since 2012, I have been developing the code to study the crystal packing of  small molecules such as ice, ammonia, methane which are of great interests in planetary science. As such, I implemented a method based on the evolutionary algorithms into the [USPEX](/research/uspex) code. In the past years, We have successfully solved a series of elusive crystal structures of a number of molecules which were unable to be fully determined in experiment. In 2015, I also participated the sixth Blind Test for Organic Structure Prediction organized by Cambridge Crystallographic Data Centre (CCDC). Among the five proposed challenges, our team successfully solved the two challenges which are rigid molecule and co-crystal made of nearly rigid molecules. Now we are able to do better with the improved methods. We welcome any collaboration from experiment and theory who has relevant projects in planetary sciences, pharmaceutics, pigments, high energy explosives and organic semiconductors.

<figure>
	<a href="/assets/images/organic-crystal-polymorphism/organic-crystals.jpg"><img src="/assets/images/organic-crystal-polymorphism/organic-crystals.jpg"></a>
	<figcaption><b>Figure 1. Some selected examples.</b></figcaption>
</figure>

See [APS Highlights](https://www.aps.anl.gov/APS-Science-Highlight/2017-05-03/an-earth-bound-amino-acid-that-may-be-common-in-outer-space)

See [ESRF Highlights](http://www.esrf.eu/home/UsersAndScience/Publications/Highlights/highlights-2016/SOM/SOM06.html)

# New code development
While the previous EA-CSP method has been successfully applied to many molecules. It is getting difficult to maintain the code and implement new functions. Since 2018, my group began to work on a new code _[PyXtal](/research/pyxtal)_ to provide a more fundamental tool to facilitate the crystal structure prediction. 

![pxtal](https://raw.githubusercontent.com/qzhu2017/PyXtal//master/images/256px_type1.png)
![water](https://raw.githubusercontent.com/qzhu2017/PyXtal//master/images/water.gif){: width="400px" style="float:right" }


# Relevant works
1. Fredericks S., Sayre D., Zhu Q. (2019).
__[PyXtal: a Python Library for Crystal Structure Generation and Symmetry Analysis](https://arxiv.org/abs/1911.11123)__. (Open Access: [PDF](https://arxiv.org/pdf/1911.11123.pdf))


1. Yang J-X, Zhu, X-L, Hu, C-H, Qiu, M-D, **Zhu, Q**, Ward, M. D and Kahr B (2019)
__[Inverse Correlation between Lethality and Thermodynamic Stability of Contact Insecticide Polymorphs](https://pubs.acs.org/doi/abs/10.1021/acs.cgd.8b01800)__
Cryst. Growth Des.,, 19, 183-1844 ([pdf](/assets/pdfs/papers/2019-acs.cgd.pdf))

1. Tan M, Shtukenberg AG, Zhu SC, Xu WQ, Dooryhee E, Nichols SM, Ward WD, Kahr and **Zhu, Q**, (2018)
__[ROY revisited, again: the eighth solved structure](https://pubs.rsc.org/en/content/articlelanding/2018/fd/c8fd00039e#!divAbstract)__
Faraday Discussion, 211, 477-491 [html]

1. Yang JX, Hu CT, Zhu XL, Zhu Q, et al (2017) 
__[DDT Polymorphism and the Lethality of Crystal Forms](http://onlinelibrary.wiley.com/wol1/doi/10.1002/anie.201703028/full)__
Angew. Chem. Int. Ed., 56, 10165-10169 

1. Shtukenberg AG, Hu CT, **Zhu Q**, et al (2017) 
__[The Third Ambient Aspirin Polymorph](http://pubs.acs.org/doi/abs/10.1021/acs.cgd.7b00673)__
Cryst. Growth Des., 17, 3562-3566 ([pdf](/assets/pdfs/papers/aspirin-2017-CGD.pdf)) 

1. Shtukenberg AG, **Zhu Q**, et al (2017) 
__[Powder diffraction and crystal structure prediction identify four new coumarin polymorphs](http://pubs.rsc.org/en/content/articlehtml/2015/sc/c7sc00168a)__
Chemical Science, 8 4926-4940 [pdf](https://pubs.rsc.org/en/content/articlepdf/2017/sc/c7sc00168a)

1. Xu W, **Zhu Q**, Hu CT (2017). 
__[Structure of Glycine Dihydrate: Its implications to Crystallization of Glycine from Solution and Modification of Glycine in Space](https://onlinelibrary.wiley.com/doi/abs/10.1002/ange.201610977)__ 
Angew. Chem. Int. Ed., 129, 2062-2066 [pdf](/assets/pdfs/papers/glycine-2017-Angew.pdf) [APS highlights](https://www.aps.anl.gov/APS-Science-Highlight/2017-05-03/an-earth-bound-amino-acid-that-may-be-common-in-outer-space)

1. **Zhu Q**, Oganov AR, Glass CW, Stokes H.(2012). 
Constrained evolutionary algorithm for structure prediction of molecular crystals: methodology and applications. 
Acta. Caryst. B68, 215-226


