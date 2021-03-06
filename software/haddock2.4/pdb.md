---
layout: page
tags: [Jekyll, HADDOCK, Bonvin, Docking, Simulation, Molecular Dynamics, Structural Biology, Computational Biology, Modelling, Protein Structure]
modified: 2014-08-08T20:53:07.573882-04:00
comments: false
title: HADDOCK2.4 manual - PDB files
image:
  feature: pages/banner_software.jpg
---

**Note:** We advise you to consult our [online tutorial](/education/HADDOCK-local-tutorial) about the local installation and use of HADDOCK2.4 where you will find many more tips and instructions to prepare your PDB files for docking.

<hr>

In order to run HADDOCK you need to have the structures of the molecules (or fragments thereof) in PDB format. There are a few points to pay attention to when preparing the PDBs for HADDOCK.

*   Make sure that all PDB files end with an END statement

*   HADDOCK will check from breaks in the chain (e.g. missing density in crystal structures or between the two strands of a DNA molecules). In the case of multiple chains within one molecule (e.g. DNA) or in the presence of co-factors, it is however recommended to add a TER statement in between the chains/sub-molecules.

*   If your molecule consists of multiple chains with overlapping numbering you will have to renumber those (or shift the numbering of some parts) in order to avoid overlapping numbering. HADDOCK will treat each molecule with a single chainID and overlap in numbering will lead to problems. Refer for detailed instruction on this topic to our [online local installation tutorial](/education/HADDOCK-local-tutorial). 

*   When starting from an ensemble of structure like, for example, from an NMR PDB entry, split structures into single PDB files. Make sure that each structure file ends with an END statement and does not contain any SEGID. Refer for detailed instruction on this topic to our [online local installation tutorial](/education/HADDOCK-local-tutorial).

*   HADDOCK can deal with ions. You will have however to make sure that the ion naming is consistent with the ion topologies provided in HADDOCK (check for this the **_ion.top_** file in the **toppar** directory. For example, a CA heteroatom with residue name CA will be interpreted as a neutral calcium atom. A doubly charged calcium ion should be name CA+2 with as residue name CA2 to be properly recognized by HADDOCK.

    (See also the [FAQ](/software/haddock2.4/faq#ions){:target="_blank"} for docking in the presence of ions).


<hr>

**Note:** Most of the tasks mentioned above can also be performed using our PDB-tools python scripts ([Rodrigues et al. F1000 Research](https://doi.org/10.12688/f1000research.17456.1){:target="_blank"}) to manipulate PDB files, select and rename chains and segids, renumber residues... and much more! See for this our [GitHub repository](https://github.com/haddocking/pdb-tools){:target="_blank"}. Some examples are also provided in the [HADDOCK2.4 local installation](/education/HADDOCK24/HADDOCK24-local-tutorial/#preparing-pdb-files-for-docking){:target="_blank"} tutorial.


