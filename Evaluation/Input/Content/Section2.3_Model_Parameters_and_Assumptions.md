### 2.3.1 Absorption

Propofol is only administered intravenously.

### 2.3.2 Distribution

Takizawa et al. ([Takizawa 2005](#5-references)) published a fu in humans to be 0.024. Mazoit et al. ([Mazoit 1999](#5-references)) reported that propofol binds to almost exclusively to serum albumin as plasma protein, which is built-in as such in the PBPK model.

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation and cell permeability calculation by PK-Sim standard. Specific organ permeability normalized to surface area was automatically calculated by PK-Sim.

### 2.3.3 Metabolism and Elimination

Propofol undergoes fast biotransformation to different metabolites.([Restrepo 2009](#5-references))  *In vitro* studies show that particularly the UGT1A9 ([Court 2005](#5-references)) is involved, followed by CYP2B6 ([Oda 2001](#5-references)).

Al-Jahdari et al. ([Al-Jahdari 2006](#5-references)) investigated the contribution of the liver and kidneys to propofol metabolism in humans using an *in vitro–in vivo* scale up approach. Human kidney and liver microsomal incubations confirmed the dominant role of UGT metabolism for propofol. Propofol was in particular metabolized by UGT1A9 and CYP2B6. The apparent arithmetic mean unbound K<sub>m</sub> (K<sub>m,u</sub>) values in the liver for the glucuronidation and hydroxylation of propofol by UGT1A9 and CYP2B6 were 0.12 (standard deviation (SD): 0.072) and 0.0072 (SD: 0.0) mM, respectively. ([Al-Jahdari 2006](#5-references)) The corresponding V<sub>max</sub> values (nmol/min/mg protein) were 2.40 (SD: 0.2) for UGT1A9, and 1.08 (SD: 0.1) for CYP2B6. In the kidney the K<sub>m,u</sub> and V<sub>max</sub> values for glucuronidation by UGT1A9 were 0.38 (SD: 0.19) mM, and 7.97 (4.5) (nmol/min/mg protein), respectively. The K<sub>m,u</sub> and V<sub>max</sub> for hydroxylation were reported to be negligible. ([Al-Jahdari 2006](#5-references))

The abundance of proteins in different organs in PK-Sim is calculated from relative expression values. For each organ, the relative expression defines the concentration of the protein in whole organ as a fraction of a defined reference concentration value. The relative gene expressions for both UGT1A9 and CYP2B6 are derived from reported Reverse Transcription-Polymerase Chain Reaction (RT-PCR) values by Nishimura et al. ([Nishimura 2006 ](#5-references)) 

The reported 25.9 pmol/mg UGT1A9 protein expression level in human liver microsomes (HLM) by Ohtsuki et al. ([Ohtsuki 2012](#5-references)) was used to calculate the reference concentration imputed in PK-Sim. The relationship between age and human microsomal protein (MPPGL) observed by Barter et al.  ([Barter 2007](#5-references)) is estimated 40 mg/g for a 30 year old individual. As the expression of UGT1A9 is highest in the kidney and relatively 10% in the liver ([Nishimura 2006 ](#5-references)), this resulted in a reference concentration of 10.36 µmol/L liver tissue for UGT1A9 which is imputed in PK-Sim. For CYP2B6, which is mainly expressed in the liver, the reported CYP2B6 protein expression level of 1.56 µmol /L liver tissue by Rodriguez et al. ([Rodrigues 1999](#5-references)) is imputed as reference concentration in PK-Sim. The reported expression level in HLM for CYP2B6 is 39 pmol/mg microsomal protein. ([Rodrigues 1999](#5-references))

For the estimation of propofol clearance in PK-Sim, K<sub>cat</sub> is estimated, which is Vmax/protein expression level in HLM. 

Although UGT1A9 expression is highest in the kidney ([Nishimura 2006 ](#5-references)), as no measurement results were available for CYP2B6 mediated hydroxylation in the kidney, the reported liver *in vitro* Km,u and Vmax values for UGT1A9 and CYP2B6 were included in the model. Reported Vmax values were in units nmol/min/mg protein and thus not directly transferable into the PBPK model. Therefore, a joint scaling factor f<sub>activity </sub> on the *in vitro* K<sub>cat</sub> values was estimated to match observed *in vivo* data, and keeping the relative relationship between those *in vitro* values (0.89 and 0.53 nmol/min/mg) for UGT1A1 and CYP2B6 fixed according to:

K<sub>cat, UGT1A9</sub> = f<sub>activity </sub> *  K<sub>cat, in-vitro, UGT1A9</sub>

K<sub>cat, CYP2B6</sub> = f<sub>activity </sub> *  K<sub>cat, in-vitro, CYP2B6</sub>

It is especially important to fix the relative contribution of both enzymes as a ratio to ensure that, when translating to other populations (e.g. children where both enzymes may undergo a different ontogeny pattern, or patients who have differently reduced amounts of UGT1A1 vs CYP2B6) the relative contributions can be adequately scaled. 
Note that the estimated scaling factor f<sub>activity</sub> will be directly implemented into the final *in vivo* V<sub>max</sub> values (only K<sub>cat, UGT1A9</sub> and K<sub>cat, CYP2B6</sub> will be reported in [section 3](#3-results-and-discussion)).

Finally, as ~0.3% of the dose is excreted in human urine as unchanged parent compound, GFR is introduced in the propofol PBPK model.
