---
sidebar_label: 'What data is available'
sidebar_position: 7
---

# 

# What data is available

This page goes through what data is available in the sandbox and how to access it. It is a work in progress and will be updated as more data becomes available.

## TRE folders and what is in them

PseudoNHS number serves as a unique identifier for individuals and is used for health data and phenotype identification.
Oragene ID consists of a 14-digit code, like `15123456789012`, and serves as an identifier for saliva tube DNA IDs. Multiple samples may be collected from the same individual, resulting in a many-to-one relationship between Oragene ID and NHS number.
Genetic assays, such as exome sequencing or GSA chip analysis, are assigned assay IDs. For GSA chip analysis, the assay ID consists of the Oragene ID concatenated with the Illumina chip ID and row position. Exome sequencing assay IDs follow the format `GNH-15123456789012_2`, with the suffix accommodating multiple assays of a single Oragene ID. Multiple or repeated assays may be conducted on the same Oragene ID.

There is a file linking Oragene ID (for genetics & questionnaire data) with PseudoNHS number (for NHS e-health record data). This file may get updated and re-dated:

```bash
/library-red/genesandhealth/2022_05_12_pseudoNHS_oragene_withmissing_DEIDENTIFIED.txt
```

Illumina GSAv3EAMD genotyping chip and TOPMed-r2 imputation data:

```bash
/library-red/genesandhealth/GSAv3EAMD/
```

Exome sequencing data. As of February 2022 n=5236 low/mid depth samples sequenced at Wellcome Sanger Institute and funded by Wellcome Sanger Institute are available. Both aligned cram files and callset vcfs are available. The file 5236_cram_IDlinkage.xlsx links Oragene IDs with multiple ID types used by Wellcome Sanger Institute. Industry Consortium funded exome sequencing data on the full 50,000+ Genes & Health volunteer cohort during 9 month post datafreeze priority period will only be available in /consortiumpriorityperiod-library-red/ After the priority period data will go into:

```bash
/library-red/genesandhealth/exome_seq/
```

Phenotypes which have been manually or automatically curated for consistency:

```bash
/library-red/genesandhealth/phenotypes_curated/
```

See also [this document](https://docs.google.com/spreadsheets/d/1ipwdF2j_owfr_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing) which has data descriptions, case counts, and phenotype codelists.

'Raw' phenotype and health record data (NHS numbers pseudonymised, and deidentified of names, postcodes, dates of birth etc).

```bash
/library-red/genesandhealth/phenotypes_rawdata/
```

Data is organised by provider and data sharing agreement. This is so we can easily change access if any of the terms of data sharing change.

Please note as of Feb 2023, we do not yet have permission from NHS Digital to put their data in the TRE. An amendment is awaited.

A reference for the NHS Digital Data Model and dictionary can be found on [NHS Digital reference](https://digital.nhs.uk/data-and-information/data-tools-and-services/data-services/hospital-episode-statistics/hospital-episode-statistics-data-dictionary).


The `genesandhealth` folder contains downloadable data 'publicly' available to users (read-only):

```bash
/library-green/genesandhealth/
```
Please see the README files in each folder for detail, e.g.,as of February 2022 there is regenie GWAS data on ~180 phenotypes.
