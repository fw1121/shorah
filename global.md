---
layout: slate_mod
title: Global analysis made simple
permalink: global.html 
---
### Generally speaking
The global analysis is performed by running `shorah.py` on the input [sorted
bam file](input.html). This will perform a shotgun [local analysis](local.html),
followed by a global haplotype reconstruction and a frequency estimation.
The output is a file with extension `.global_haps.fasta`. It is a fasta file
with all the reconstructed haplotype sequences, with the header indicating the
frequency after the underscore. So, for example

    >HAP0_0.264857
    CCTCAGATCACTCTTTGGCAACGACCCCTCGTCACAATAAAGATAGGGG

means that the haplotype was estimated to have a frequency of 26.5%.

This file is a selection of the most frequent among all reconstructed
haplotypes. These are in the file with extension `.popl`.

### A word of caution
Inferring haplotypes over a region longer than the reads is hard. Many false
positives can be introduced if reads are shorter than the region one would need
to observe to capture enough diversity. See the references

- [_Zagordi et al._ (2012) PLoS ONE][zagordi2012]

- [_Beerenwinkel, Zagordi_ (2011) Curr. Opin. Vir][beerenwinkel2011]

- [_Beerenwinkel et al._ (2012) Front. Microb.][beerenwinkel2012]


The `.popl` file will typically contain many haplotypes, most of which at
very low frequencies. You are advised not to give high confidence to
haplotypes at frequency below a certain threshold that depends from case
to case. Other software you could use for global reconstruction

- [QuasiRecomb](http://www.bsse.ethz.ch/cbg/software/quasirecomb),
  by [Armin Toepfer](https://github.com/armintoepfer)

- [PredictHaplo](http://bmda.cs.unibas.ch/HivHaploTyper/index.html)

[zagordi2012]: http://dx.doi.org/10.1371/journal.pone.0047046 "PLoS ONE"
[beerenwinkel2011]: http://dx.doi.org/10.1016/j.coviro.2011.07.008 "Curr. Opin Vir."
[beerenwinkel2012]: http://dx.doi.org/10.3389/fmicb.2012.00329 "Front. Microb."

---

Go back [home](index.html)