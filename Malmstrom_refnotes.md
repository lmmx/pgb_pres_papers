## Proteome-wide cellular protein concentrations of the human pathogen Leptospira interrogans




[Recommended on F1000 Prime by Mathieu Picardeau at *Institut Pasteur*](http://f1000.com/prime/1164477):

> <sub>This impressive study determines protein concentrations at the single cell level in a bacterial pathogen.

> <sub>The authors combined quantitative mass spectrometry and cryo-electron tomography to determine the copy number of specific proteins in the pathogen Leptospira interrogans. Abundance of proteins was estimated for more than half of the predicted coding sequences. The information gained from this study will contribute to our understanding of the biology of this understudied human pathogen. This method can also be applied to other organisms.



### Paper introduction

> MS-based methods for relative proteome quant. have broadly affected life science research

Followed by a 2010 study ["Proteome-wide protein concentrations in the human heart"](http://dx.doi.org/10.1039/c004495d)

This study presents **methodology to quantify absolute concentrations** [no. protein copies per cell in a population] **for a large fraction of the proteome in <u>genetically unperturbed</u> cells**

* Ref. 1: [Ghaemmaghami 2003](http://dx.doi.org/10.1038/nature02046), example of such genetic perturbation


### Cited in Handbook of systems biology <small>(p10, in Ch. 1)

This is an example of bottom-up approaches typical to proteomics, whereby broken down (digested) protein is reconstructed *in silico* (disadvantage here is loses information about the entire protein, such as co-occurring modifications, but experimentally less difficult.

> * p4
<small>The development of relative and absolute quantification methods over the last decade has been particularly crucial to proteomics. Using the latest proteomics technologies, it is now possible to quantify essentially complete proteomes of model organisms such as yeast. More complex organisms are also coming within reach.<br/>
Protein amount, localization, modification state, turnover and interactions can all be measured with increasing precision and increasingly sophisticated approaches, as detailed below. There is a unique opportunity to employ these data as a crucial underpinning for building accurate and comprehensive models of the cell
</small>

</small>







### Beck (2011) [Exploring the spatial and temporal organisation of a cell's proteome](http://dx.doi.org/10.1016/j.jsb.2010.11.011)

* second class of research techniques described: "*research that visualizes the spatial distributions of these complexes within the cellular context using cryo electron tomography techniques combined with computational image processing*"
* cryoET can be applied to a [pleomorphic](https://en.wikipedia.org/wiki/Pleomorphism_(cytology)) biological specimen in its **near native state**, not only determining ultrastructure (membrane-bound compartmentalization) but 3D snapshots of distributions of large complexes inside the cell
* **quantitative MS can provide info about which types of proteins are active at a single point in time, and the relative and absolute abundance and their assemblies in cells and organelles**
* spatial gradients, irregularities and discontinuities of macromol. distributions are known to play an active role in biological process (cel division, genome segregation, gene reg., cell morhphogenesis, shape maintenance) and general signaling...

> <sub>High-resolution structures of macromolecular complexes provide major insights in their molecular mechanism. But to fully understand their function in the context of cellular processes, knowledge of their spatial distribution within living cells is crucial.

* at the currently achievable resolution only large protein complexes have a chance of being identified and **the low signal-to-noise ratio peculiar to cryoET hampers a robust and reliable detection**
* visual proteomics approaches are [so far] dependent on available template structures, i.e. biased by their own template libraries. To generate libraries of template structures that best account for the signal observed in a cryoET, the imaging process has to be simulated as realistically as poss., first the imaged quantity is calculated from coord's and identities of atoms specified in PDB. Subsequently, density is convoluted with [contrast transfer function](https://en.wikipedia.org/wiki/Contrast_transfer_function), which describes imaging in the TEM in linear approximation ([Lucic 2005](http://dx.doi.org/10.1146/annurev.biochem.73.011303.074112)).




* there are also *biological* aspects to be taken into account when template libraries are being assembled. **Can the template account for the structural state of the targeted molecule within the cell?**
  * [Han 2009](http://dx.doi.org/10.1073/pnas.0813068106): high structural diversity between different microorganisms, meaning **selection of reference structures solved from other species has therefore to be done with caution**.
  * protein complex might exist in diverse oligomeric states in the cell that might differ from the spiecies observed during structure determination.
     * for this reason visual proteomics approaches so far were limited to **highly stable** and **conserved** targets.
     * The abundance of the targeted protein complexes in the cell and the extent to which the template library accounts for all large protein complexes that exist in the cell is important, as high abundant protein complexes of similar structure might compete for assignments and thereby have negative effect on performance.
     * Malmstrom 2009 is an example of how **targeted and directed MS measurements** can provide required auxiliary info about protein abundances on a proteome-wide scale.

`On the Leptospira interrogans study`






* Targeted proteomics experiments detecting the identity and concentrations of cellular proteins were combined with cryoET-based template-matching to detect spatial localisations of a set of protein complexes
* to identify template structures that might be suitable for the template matching, 26 candidate assemblies >250 kDa and with a certain sequence conservation were retrieved from structural databases
* protein abundance ranged over 3.5 orders of magnitude, only 10 other protein complexes of sufficient ize for matching were found with aundances of >100 copies per cell
* tomograms acquires and subjected to template matching and scoring
* local conc. of targeted protein complexes varied within and across datasets (cells displayed avg. ribosome conc. of ~20μM in cytoplasm, local conc. ranging from 5 to 30μM
   * local conc. of GroEL together with GroEL-ES were larger and ranged from ~8 to 100 μM






* **This study showed that**:
  * background noise reduces performance depending on [MTF](http://photo.net/learn/optics/mtf/) (performance) of the CCD camera
  * the missing wedge can introduce angular bias to discoery rate of templates with anisotropic signal (such as elongated ATP synthase)
  * specificity increases with template abundance
  * specificity decreases with degree of molecular crowding
* The last two effects are **more pronounced for smaller templates**. Specificity achieved for high abundant MDa complexes was concluded satisfactory. True positive discovery rates higher than 50% are difficult to achieve when protein complexes of smaller M<sub>W</sub> are targeted. Complexes of very low cellular abundance are challenging to statistically model

Throughput limitations lie in cryoEM as shown by work on *P. pneumoniae* by [Yus 2009](http://dx.doi.org/10.1126/science.1177263), [Kuhner 2009](http://dx.doi.org/10.1126/science.1176343), [Guell 2009](http://dx.doi.org/10.1126/science.1176951)).

* nevertheless, demonstrated power of mapping macromolecular structures into entire-cell tomograms when combined with unbiased large-scale complex purification techniques. Template library was in part built here from single-particle EM structures of *M. pneumoniae* protein complexes, overcoming problematic assumption of structural conservation across species
