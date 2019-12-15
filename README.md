# G4003-ORDO-SNOMED
Public repo for BINF G4003 final project: Mapping Disease Representations from Orphanet Rare Disease Ontology to SNOMED-CT
*Janice Yang, Liangyu Zhao, Rong Ma, Zhenyu Zhang*

## Automated mapping
Full code is found in ORDO_to_SNOMED.ipynb notebook file. The sequential steps in our mapping method:
1. Case-insensitive exact string match to SNOMED disorder-tagged terms
2. Find SNOMED atoms from existing UMLS CUI mappings, where available
3. First-pass SNOMEDCT_US-restricted MetaMap: map if output is a single term with mapping score 1000
4. Use existing ICD10 mappings, find corresponding SNOMED term if available, then get best fuzzy string match between ORDO concept and its synonyms, and the SNOMED term and its children terms.
5. Re-run MetaMap on all remaining terms and use SNOMED's post-coordination format for combining, refining, or qualifying terms.
More details on the complete algorithm can be found in our final paper writeup.

## Guide
-Folder ORDO_info: Stores unmapped terms from each step as input into next step. Also contains ICD-SNOMED mapping dictionary.
-File ORDO_to_SNOMED.ipynb: full code for automated mapping of ORDO disease terms-->SNOMED CT.
-File replace_utf8.jar: Convert output files to UTF-8 encoding.
-Folder Results: Stores mapping results.
-Folder Vocabularies: Placeholder for folder to store vocabulary release files.
