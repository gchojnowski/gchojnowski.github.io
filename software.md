---
layout: page
title: Software
permalink: /software/
---

## Characterization of protein-protein interactions using AlphaFold

<img src="/data/contacts.jpg" style="float:left;width:500px;margin:0px;">

One of the hardest parts of macromolecular crystallography and cryo-EM is making sense of the structural models. We don't use clay and wire to build them anymore, but the models have got bigger and the time pressure has got stronger over time. One of the problems associated with this - model validation - I have addressed with [checkMySequence](https://gitlab.com/gchojnowski/checkmysequence). However, there are cases where a model can be fitted into a map, but the resolution is too low to confirm its identity. Similarly, the resolution of the map may not allow the identification of contacts that are critical for functional analysis.

I have developed a tool based on AlphaFold2 - **gapTrick** - that helps to solve these problems. In principle, it rebuilds protein models, but it can also identify contacts at protein-protein complex interfaces. They are more reliable than confidence scores (pTM or ipTM) and very precise. Finally, gapTrick uses monomeric AlphaFold2 models and there is no training set bias that many AI-based tools suffer from!

I use it a lot for cryo-EM model building. Several fascinating stories will soon appear in the [Structure stories](/models) section, stay tuned!

 - Chojnowski [bioRxiv (2025) 01.31.635911](https://doi.org/10.1101/2025.01.31.635911)
 - [https://github.com/gchojnowski/gapTrick](https://github.com/gchojnowski/gapTrick/tree/main)

<br/>

## Sequence information identification and validation in EM and MX

<img src="/data/checkmysequence.jpg" style="float:left;width:500px;margin:0px;">

Sequence assignment is a critical step in macromolecular modelling in EM and MX, and often leads to hard-to-detect errors. The availability of AI-based predicted models hasn't changed this. I have developed a suite of programs for the identification and validation of sequence information in models of macromolecules solved using EM and MX. The programs are avilable in [CCP4](https://www.ccp4.ac.uk/), [CCP4Cloud](https://cloud.ccp4.ac.uk/), [CCPEM/doppio](https://www.ccpem.ac.uk/), and on [https://gitlab.com/gchojnowski/](https://gitlab.com/gchojnowski/)
 - Chojnowski, "doubleHelix: nucleic acid sequence identification, assignment and validation tool for cryo-EM and crystal structure models" [Nucleic Acids Research 2023. 51(15): p. 8255–8269](https://doi.org/10.1093/nar/gkad553)

 - Chojnowski "Sequence-assignment validation in protein crystal structure models with checkMySequence." [Acta Cryst D (2023)](https://doi.org/10.1107/S2059798323003765)

 - Chojnowski "Sequence-assignment validation in cryo-EM models with checkMySequence." [Acta Cryst D (2022): 806-816](https://doi.org/10.1107/S2059798322005009)

 - Chojnowski et al. "findMySequence: a neural-network-based approach for identification of unknown proteins in X-ray crystallography and cryo-EM." [IUCrJ 9.1 (2022): 86-97](https://doi.org/10.1107/S2052252521011088)


<br/>
## _De novo_ model building in EM and MX

Before AlphaFold2 came along, ARP/wARP was one of the leading programs for modelling macromolecular crystal structures. I have made several contributions to the suite, including adapting it for modelling EM models. The programs are avilable in [CCP4](https://www.ccp4.ac.uk/) and [CCP4Cloud](https://cloud.ccp4.ac.uk/),

 - Chojnowski et al. "The accuracy of protein models automatically built into cryo-EM maps with ARP/wARP." [Acta Cryst D (2021): 142-150](https://doi.org/10.1107/S2059798320016332)

 - Chojnowski, Pereira, and Lamzin. "Sequence assignment for low-resolution modelling of protein crystal structures." [Acta Cryst D (2019): 753-763](https://doi.org/10.1107/S2059798319009392)

 - Chojnowski et al. "The use of local structural similarity of distant homologues for crystallographic model building from a molecular-replacement solution." [Acta Cryst D (2020): 248-260](https://doi.org/10.1107/S2059798320000455)


<br/>
## Fragment based modeling of RNA structures

<img src="/data/rnamasonry.jpg" style="float:left;width:380px;margin-right:30px;">

Structured RNA molecules often share structural motifs. I have developed a suite of programs for analysing existing RNA models ([RNA Bricks](https://genesilico.pl/rnabricks2/) database) and reassembling them with experimental restraints (BrickworX, RNAMasonry).

On the left is an example of a model of a viral RNA molecule built with [RNA Masonry](https://iimcb.genesilico.pl/rnamasonry) using experimental Small Angle X-ray Scatering (SAXS) data. RNAMasonry assembles models of RNAs from large, recurrent framents, signifficantly reducing the number of degrees of freedom. This is particularly important when building a 3D model of hundreds of nucleic acid residues from a 1D experimental SAXS curve with only a few independent data points.


 - Chojnowski et al. "Brickworx builds recurrent RNA and DNA structural motifs into medium-and low-resolution electron-density maps." [Acta Cryst D (2015): 697-705](https://doi.org/10.1107/S1399004715000383)

 - Chojnowski, Waleń, and Bujnicki. "RNA Bricks—a database of RNA 3D motifs and their interactions." [Nucleic acids research 42.D1 (2014): D123-D131](https://doi.org/10.1093/nar/gkt1084)

 - Chojnowski et al. "RNA 3D structure modeling by fragment assembly with small-angle X-ray scattering restraints." [Bioinformatics 39.9 (2023): btad527](https://doi.org/10.1093/bioinformatics/btad527)

<br/>
## Unusual signals in protein crystal diffraction patterns

Series of publications from my PhD on the identification of unusually strong signals in protein crystal diffraction patterns using statistical analysis based on the Extreme Value Distribution Theorem. The initial idea was to see if one could find signals associated with secondary structure elements (e.g. alpha helices) and use them for molecular replacement. However, these turned out to be too weak to be able to pick out the poseudo-random fluctuations. I used this idea to write a program called DIBER, which identifies RNA/DNA helices based on diffraction patterns alone, before the crystal structure is solved.

 - Chojnowski, Bujnicki, and Bochtler. "RIBER/DIBER: a software suite for crystal content analysis in the studies of protein–nucleic acid complexes." [Bioinformatics 28.6 (2012): 880-881](https://doi.org/10.1093/bioinformatics/bts003)

 - Chojnowski and Bochtler. "DIBER: protein, DNA or both?." [Acta Cryst D (2010): 643-653](https://doi.org/10.1107/S090744491000781X)

 - Chojnowski and Bochtler. "The statistics of the highest E value." [Acta Cryst A (2007): 297-305](https://doi.org/10.1107/S010876730701848X)

 - Bochtler and Chojnowski. "The highest reflection intensity in a resolution shell." [Acta Cryst A (2007): 146-155](https://doi.org/10.1107/S0108767306052809)
