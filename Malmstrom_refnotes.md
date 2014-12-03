## Proteome-wide cellular protein concentrations of the human pathogen Leptospira interrogans




[Recommended on F1000 Prime by Mathieu Picardeau at *Institut Pasteur*](http://f1000.com/prime/1164477):

> <sub>This impressive study determines protein concentrations at the single cell level in a bacterial pathogen.

> <sub>The authors combined quantitative mass spectrometry and cryo-electron tomography to determine the copy number of specific proteins in the pathogen Leptospira interrogans. Abundance of proteins was estimated for more than half of the predicted coding sequences. The information gained from this study will contribute to our understanding of the biology of this understudied human pathogen. This method can also be applied to other organisms.



### Paper introduction

> MS-based methods for relative proteome quant. have broadly affected life science research



#### MS 1: LC-ESI

#### MS 2: absolute quantification of 19 proteins (targeted SRM)

#### MS 3: LC-MS/MS

* Extracted precursor ion intensities for peptides derived from LC-MS maps acquired from trypsinized cell lysates
* Calculated total protein ion intensity for the respcetive proteins by using median intensities from the three most intense peptides matching to a specific protein (refs 9-11: Silva 2006, Vogel 2008, Ishihama 2005)






Mueller 2007 presented an OSS tool called *SuperHirn*, a set of modules to process LC-MS data acquired on a high-res. MS. Includes: feature extraction and quantification, LC-MS similarity analysis, LC-MS alignment of multiple datasets and **intensity normalisation**.

> <sub>These program routines extract profiles of measured features and comprise tools for clustering and classification analysis of the profiles.

 > <sub>Only a small subset of peptide features in the sample are selected for fragmentation analysis leading to a systematic undersampling of peptide identifications in conventional shotgun LC-MS experiments ([Li 2005](http://dx.doi.org/10.1074/mcp.M500141-MCP200)).
 
 > > <sub>There is an increasing interest in the quantitative proteomic measurement of the protein contents of numerous, substantially similar samples. Typical examples include the discovery of protein biomarkers from clinical samples (3, 22, 23) and the measurement of the response of cells and tissues to perturbations. For biomarker discovery, large numbers of samples need to be processed to achieve sufficient statistical power to distinguish disease-specific markers from coincidental proteome fluctuations within the human population. For the study of cellular response to perturbations, temporal and dose-de- pendent changes are usually particularly informative for the identification of patterns of proteins that are specifically affected by the treatment (24). Therefore, these and similar applications require high sample throughput and highly reproducible coverage of the proteome.

> > <sub>**Quantitative LC-MS/MS is of limited use for such large scale studies because of significant undersampling** of complex proteomic samples. Even after extensive peptide fractionation, **a significant fraction of the peptides present in a sample is not selected by the mass spectrometer** for [CID](https://en.wikipedia.org/wiki/Tandem_mass_spectrometry#Collision-induced_dissociation) [collision-induced dissociation]. These peptides are neither identified nor quantified. Therefore, **if multiple, substantially similar samples are being analyzed, the fraction of those peptides that is measured in every sample rapidly decreases with increasing sample number**. Furthermore the peptides that are consistently detected tend to be the high abundance peptides that generate intense MS signals, whereas **many lower abundance, biologically interesting peptides are inconsistently sampled**. As a result, **it is very difficult to consistently obtain quantitative information on low abundance proteins across multiple samples by the LC-MS/MS**.




> <sub>An alternative to an MS2-based approach is the analysis of peptide ion currents directly at the MS1 level that allows mapping of extracted peptide features across LC-MS experiments. For this purpose, feature extraction routines detect peptide signals in noisy background and compute the ion counts of selected peptides (SIC) without relaying on MS2 peptide identification information. Even though the comparison of absolute SIC values is complicated by experimental verification, the application of peptide signal intensity normalization methods allows restoring the linear correlation between the original peptide concentration and the measured signal intensity. These properties offer an **alternative to the costly isotopic labeling strategies** where chemically modified peptides are compared within the same LC-MS experiment.












> <sub>While quantification based on stable isotope labeling seems to be **more accurate**, it involves more extensive sample processing if more than two (or four in the case of iTRAQ) samples are compared ([Meng 2007](http://dx.doi.org/10.1016/j.jasms.2006.09.014)).

> ><sub>Peak intensity variability is inherent in label-free LC-MS experiments, and this variability can arise from multiple sources, including biochemical sample processing (enzymatic digestion, reductive alkylation, etc.) and LC-MS profiling (e.g., variation in sample injection or electrospray condition)</blockquote>

* Malmstrom (2006) [*Optimized peptide separation and identification for MS-based proteomics via free-flow electrophoresis*](http://dx.doi.org/10.1021/pr0600632)

and

* Yi (2003) [*A microcapillary trap cartridge-microcapillary HPLC ESI emitter device capable of peptide MS2 at the attomole level on an ion trap MS with automated routine operation*](http://dx.doi.org/10.1002/rcm.1150)

describe the HPLC-MS/MS method. Notable difference is IEF over ion exchang separation of peptides in the first dimension:

* multidimensional LC-MS based shotfun proteomics traditionally 1) ion exchange, 2) RP-LC. IEF improved by **continuous [free-flow electrophoresis](https://en.wikipedia.org/wiki/Free-flow_electrophoresis)**.
* FFE is used for quant. separations, conducted in a fast and gentle liquid-based manner (no solid matrix, like polyacrylamide)
* high recovery rate - no analytes lost, hence "HP".

> <sub>An even and laminar liquid film is conducted between two plates, split up in parallel fractionation tubes, collected in microtiter plates. A high voltage field is applied perpendicular, analytes separate by charge density and isoelectric point.

* Aebersold lab incorporated the pI information as an additional [validation] parameter into a statistical model for discrimination between correct and incorrect peptide assignments to MS/MS spectra.
  * Thus incorporated pI information from *PeptideProphet*, searching MS2 spectra against non-redundant NCBI predicted proteome along with known contaminants (like keratin) to validate assignments.
  * SEQUEST gives multiple search scores for the database... PeptideProphet typically uses **the difference between measured and theoretical peptide mass**, no. of termini consistent with type of enzymatic cleavage, no, missed cleavage sites.












> <sub>The probabilities of peptide assignments to spectra are computed without taking the pI values into consideration. SEcond, for each FFE fraction, the average pI of the correctly identified peptides in that fraction is calculated by summing the theoretical (seq. determined) pI values of each peptide assignment and using the peptide probabilities obtained at the first step as weight factors.

> <sub>The standard deviation of pI values in each FFE fraction is computed in an analagous manner. Third, a standardized score (pI score) is calculated for each peptide assignment by subtracting the average pI value and dividing it by the standard deviation (using the average value and the standard deviation for the corresponding FFE fraction).

> <sub>...Inclusion of pI information in the model results in **increased probability of lower scoring peptides if they have a pI close to the average pI observed for high scoring peptides from the same fraction, and in decreased score of peptides which have a pI far away from the average pI**.

* Since the pI score is based on avg. calculated pI of the identified peptides, **the model is independent of changes in buffer conditions and temperature** which influences the pK of the analytes thus the pI function in the PeptideProphet is applicable to any type of IEF based separation independent of separation conditions.
* FFE-IEF: High sample load, short separation times and **no regeneration time** between consecutive runs, attractive for shotgun MS.


---

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
