---
layout: page
title: Structure stories
permalink: /models/
---

## EM is not for disorder — or is it?

<img src="/data/p8p5_with_insets.png" style="float:left;width:300px;margin:20px;">
Peroxisomes are essential eukaryotic organelles, yet they lack their own genetic machinery and import all proteins from the cytosol. Despite their importance and a fairly complete knowledge of the molecular components involved, the mechanism of protein import remains poorly understood.

In a recent project led by Matthias Wilmanns, Lakhan Ekal determined a medium-resolution cryo-EM structure of the key peroxisomal import receptor Pex5 in complex with its cargo Pex8, which is also likely to play a role in Pex5 recycling. Notably, nearly half of the Pex5 chain is intrinsically disordered, making it a very tough target for detailed cryo-EM analysis.

Nevertheless, by combining medium-resolution cryo-EM reconstructions with AlphaFold3 predictions using [gapTrick](https://github.com/gchojnowski/gapTrick), we were able to show that, in addition to the canonical PTS1 interaction (right), the long disordered N-terminal tail of Pex5 forms a secondary, previously uncharacterised interaction site (left).

This example nicely illustrates that combining cryo-EM with modern structure prediction can extend the interpretability of experimental data beyond what is often assumed to be possible for disordered regions.

<!-- PDB id: <a href="https://www.rcsb.org/structure/7Y7A">7Y7A</a> -->

 - Ekal et al (2025). Structure of Pex8 in complex with peroxisomal receptor Pex5 reveals its essential role in peroxisomal cargo translocation
 biorXiv doi:<a href="https://doi.org/10.1101/2025.08.30.673231">10.1101/2025.08.30.673231</a>

---

<br/>

## A needle in a haystack

<img src="/data/lhc_small.jpg" style="float:left;width:300px;margin:20px;">
The model was automatically released by the wwPDB after a standard 1 year embargo and immediately attracted a lot of attention. An <i>in situ</i> cryo-ET reconstruction of a light-harvesting megacomplex from red algae; 37MDa, 1,792 aa chains, 305,000 residues and 2.5M non-H atoms. This huge model was undoubtedly a real challenge to build. It also proved to be a challenge for the wwPDB validation tools; the model remains unvalidated.

The good news is that the model can be validated easily using [checkMySequence](https://gitlab.com/gchojnowski/checkmysequence). In about an hour, the program finds several sequence assignment and map-fit issues. One of them is particularly interesting given my background in crystallography.


Molecular Replacement (MR) is the most widely used method for solving crystal structures. It provides a rough model of the crystal structure that is later iteratively improved. It's much simpler than experimental phasing techniques, but requires a model that is very similar to the unknown macromolecule in the crystal. Usually a close homologue. As the PDB got bigger (even before AlphaFold2 came out), proteins with no known homologues became relatively rare. However, there were still cases of proteins that required experimental phasing. Once their structures were solved, it was often found that there are similar ones in the PDB already. But sequence similarity was too low to allow for identification.


The light-harvesting megacomplex turned out to contain two almost identical proteins (0.6 Å rmsd) with only 60% sequence identity, which were swapped in the model. Another example of identical proteins with low sequence similarity I faced in a short time. A protein feature desired for MR that can lead to hard-to-detect errors in EM. Remember to check your models with [checkMySequence](https://gitlab.com/gchojnowski/checkmysequence)!

PDB id: <a href="https://www.rcsb.org/structure/7Y7A">7Y7A</a>

 - You, X., Zhang, X., Cheng, J., Xiao, Y., Ma, J., Sun, S., ... & Sui, S. F. (2023). In situ structure of the red algal phycobilisome–PSII–PSI–LHC megacomplex. Nature, 616(7955), 199-206. doi:<a href="https://doi.org/10.1038/s41586-023-05831-0">10.1038/s41586-023-05831-0</a>

 - Sierk, M. L., & Kleywegt, G. J. (2004). Deja vu all over again: finding and analyzing protein structure similarities. Structure, 12(12), 2103-2111. doi:<a href="https://doi.org/10.1016/j.str.2004.09.016">10.1016/j.str.2004.09.016</a>

---

<br/>
## A tale of two dehydrogenases
<p>
<img src="/data/gamma_dehydro_small.jpg" style="float:left;width:300px;margin:20px;">

I was contacted by Panos Kastritis from the University of Halle-Wittenberg who needed help interpreting three cryo-EM reconstructions from native <i>C. thermophilum</i> cell extracts. All of them had very characteristic tertiary structures and seemed easy to identify. In addition, AlphaFold2, which was released at about the same time, gave excellent predictions for all the targets. It looked like a straightforward model building task.
</p>

After building the initial models, I checked them with a prototype of [checkMySequence](https://gitlab.com/gchojnowski/checkmysequence), a sequence assignment validation program I was working on at the time. Surprisingly, the program identified a problem with the sequence of one of the models. It was completely wrong, even though the model seemed to fit the map perfectly.

It turned out that there are two variants of oxoglutarate dehydrogenases in the _C. thermophilum proteome_. They have very similar structures (1.5Å rmsd), but share only 22% of the sequence. They are visually indistinguishable based on the 4.4Å resolution map. To resolve the ambiguity, I predicted both structures with AlphaFold2, fitted them to the map, and used for sequence identification with <a href="https://gitlab.com/gchojnowski/findMySequence">findMySequence</a>. The program assigned the same sequence variant to both backbone models, clearly confirming the identity of the protein.

If you can get rough fit of a predicted model to a reconstruction, <a href="https://gitlab.com/gchojnowski/findMySequence">findMySequence</a> will help you identify a protein even if no side chains are visible. It's a pretty powerful approach!

PDB ids: <a href="https://www.rcsb.org/structure/7Q5Q">7Q5Q</a>, <a href="https://www.rcsb.org/structure/7Q5R">7Q5R</a>, <a href="https://www.rcsb.org/structure/7Q5S">7Q5S</a>

 - Skalidis, Kyrilis, Tüting, Hamdi, ***Chojnowski***, & Kastritis (2022). Cryo-EM and artificial intelligence visualize endogenous protein community members. Structure, 30(4), 575-589. doi:<a href="https://doi.org/10.1016/j.str.2022.01.001">10.1016/j.str.2022.01.001</a>

---

<br/>
## ESX-5 Type VII Secretion System

<p>
<img src="/data/esx5_small.jpg" style="float:left;width:200px;margin:20px;">
The very last cryo-EM structure I built <b>without AlphaFold2</b>. It required all the tricks including focused refinement, <i>de novo</i> model tracing, MX, and integrative modelling to interpret the data. The most interesting part of the story is that we were (technically) scooped by a group working right next door. However, their structure corresponds to different pore conformations than ours (closed versus open), which gives some intriguing new insights into how the complex works.
Fascinating project pursued virtually during covid-19 pandemic together with a great team of friends from EMBL!
</p>

PDB id: <a href="https://www.rcsb.org/structure/7B9S">7B9S</a>

<br/>
 - Beckham \*, Ritter \*, **Chojnowski\***, et al. (2021). Structure of the mycobacterial ESX-5 type VII secretion system pore complex. Science advances, 7(26), eabg9923.doi:<a href="https://doi.org/10.1126/sciadv.abg9923">10.1126/sciadv.abg9923</a>

---

<br/>
## High resolutiuon strcuture of purine nucleoside phosphorylase
<p>
<img src="/data/pnp_small.jpg" style="float:left;width:200px;margin:20px;">
The very first crystal structure I solved. High-resolution (1.45 Å) structure models can be a pain to build (all those alternative conformations!), but the beautiful maps were a great help to a structural biology noob like me at the time. It was also the first model in the lab built using COOT, a new development back then. It quickly replaced <i>O</i> and made SGIs obsolete. 
</p>

Picture on the left shows a PNP crystal during data collection at a non-existent storage ring <a href="https://www.desy.de/e141261/e158573/e158613/index_eng.html">DORIS</a> at DESY, Hamburg. Cryo-jet has blown out most buffer from a too spacious loop, but the crystal still diffracted up to the edge of a detector.

PDB id: <a href="https://www.rcsb.org/structure/3FUC">3FUC</a>

 - **Chojnowski**, Breer, Narczyk, Wielgus-Kutrowska, et al. (2010). 1.45 Å resolution crystal structure of recombinant PNP in complex with a pM multisubstrate analogue inhibitor bearing one feature of the postulated transition state. Biochemical and biophysical research communications, 391(1), 703-708. doi:<a href="https://doi.org/10.1016/j.bbrc.2009.11.124">10.1016/j.bbrc.2009.11.124</a>
