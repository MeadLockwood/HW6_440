This repo contains code for creating a heatmap that compares transcriptomics RNAseq data from the left ventricle (LV) tissue of both normal functioning (NF) and hypertrophic cardiomyopathy (HCM) hearts. The initial RNA seq data was obtained from Morely et al. and can be found via Gene Expression Omnibus GSE141910 at https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE141910. Phenotypic data was obtained from Morely et al GitHub MAGNet repo at https://github.com/mpmorley/MAGNet.

The data was specifically generated via harvesting of left ventricle free wall tissue at the time of cardiosurgery for diseased hearts and from unused donor hearts of apparent normal function at an unspecified timepoint. Total RNA was extracted using miRNeasy Kit (Qiagen) and RNA quality and concentration were assessed by both NanoVue Plus™ spectrophotometer (GE Healthcare) and the Agilent 2100 RNA Nano Chip (Agilent). RNAseq data was generated on a Illumina TruSeq stranded mRNA kit with Nugen Ovation amplification kit. Random selection of libraries into pools of 32 was done to mitigate batch effects and sequencing was performed with a depth of ~30 million 100-bp paired-end reads per sample. Alignment was done using hg19/hGRC37 reference geneome with STAR aligner. MarkDuplicates from Picard tools was used to eliminate duplicate reads. Voom and LIMA R were used for nromalization of data. SVA package was used to create surrogate variables to account for batch effect. Finally differential gene expression between races was performed using LIMMA R utilizing a linear model which is specified at the Morely et al GitHub MAGNet repo and accounts for age, race, and sex amongst other phenotypic traits. The final RNAseq data is expressed as log2.

Final_Project_Data contains the log2 gene expression per each sample.

phenoData.csv contains the phenoData.csv for each sample.

.gitattributes contains the attributes needed for this repo.

.gitignore contains the untracked files that should be ignored.

lockwood_myers_heatmap contains a jpg figure of the heatmap.

440_lockwood_myers_project.py contains the source code (python 3.6.3) for generating heatmap that compares transcriptomics RNAseq data from the left ventricle (LV) tissue of both normal functioning (NF) and hypertrophic cardiomyopathy (HCM) hearts. This code is specific to the data structure as presented by Morely et al and was written using the Google CoLab ide. Therefore, to run this code one would need to alter file paths etc when uploading data.
