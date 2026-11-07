#Homology Modeling and Molecular Docking of TviB

Structural modeling and active-site validation of TviB, a UDP-N-acetylglucosamine 
6-dehydrogenase from *Salmonella enterica* serovar Typhi, which has no experimentally 
determined structure.

#Background

TviB catalyses the first committed step in biosynthesis of the Vi capsular 
polysaccharide — a key virulence factor and vaccine antigen in typhoid fever. No 
structure for TviB exists in the PDB, so a homology model was built to enable 
structure-based analysis.

#Methodology 

1. **Template search** — BLAST against the PDB identified Cap5O (PDB: 3OJL, 
   *Staphylococcus aureus*) as the best template, at 31.02% sequence identity.
2. **Homology modeling** — Built using SWISS-MODEL.
3. **Model validation** — GMQE (0.67), QMEANDisCo Global (0.66 ± 0.05), and 
   MolProbity/Ramachandran analysis (91.85% residues in favoured regions).
4. **Docking** — TviB's native substrate, UDP-GlcNAc, was docked using AutoDock 
   Vina (binding affinity: −9.104 kcal/mol).
5. **Active-site cross-validation** — Residues contacting the docked ligand were 
   compared, via pairwise sequence alignment (EMBOSS Needle), against the 
   template's experimentally confirmed NAD-binding residues. 13 of 20 
   docking-derived residues matched confirmed cofactor-binding positions across 
   four independent clusters.

#Key result

A binding score alone does not confirm a docking result is biologically meaningful. 
This project's cross-validation step provides reasonable, independent evidence that 
the model's predicted active site corresponds to the real, conserved region of this 
enzyme family — rather than relying on the docking score in isolation.

#Tools used

PyMOL · AutoDock Vina · AutoDockTools · SWISS-MODEL · BLAST · EMBOSS Needle

#Limitations

- Template identity (31%) is moderate, not high-confidence
- Model is apo (no cofactor bound) and monomeric (TviB's biological assembly is    a homodimer)
- Only cofactor-binding residues were used for cross-validation; no independent 
  confirmation of substrate-specific contacts was available

#Files

- `report/` — full write-up with methodology, results, and discussion
- `figures/` — docking pose visualization and Ramachandran plot
- `scripts/` — PyMOL commands and Vina configuration used
