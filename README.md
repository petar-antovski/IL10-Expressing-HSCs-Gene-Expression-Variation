# IL10-Expressing-HSCs-Gene-Expression-Variation

## Samples
- HSPCs were isolated from young naive, young transplanted, old naive and old transplanted mice and submitted for RNA sequencing.

## Data Preprocessing
- Samples for each type are combined before any pre-processing.
- Ambient RNA removal was determined to improve downstream analysis.
- Remove genes expressed in less than 3 cells and remove cells with less than 200 genes expressed.
- Remove cells with mitochondrial gene percentage higher than 10% and cells with ribosomal gene percentage las than 5%.
- Remove mitochondrial, Gm42418 and Malat1 as these are all the most highly expressed genes and are only used for previous QC steps and not necessary for downstream steps.
- No batch correction was performed as this yielded best results in terms of UMAP and downstream Gene Set Enrichment Analysis (GSEA), Differential Gene Expression Analysis (DGEA) and Gene Ontology (GO) analysis.

## Cell Annotation
- Use raw reacds for transcription based cell annotation with SingleR package using R.

## Data Analysis and Visualization
- Compute tSNE plot and UMAP using raw counts on all cell types for each group type.
- Perform GSEA on the IL10 expressing HSCs (IL10 HSCs), IL10 receptor epxressing HSCs (IL10ra HSCs), and double negative HSCs (DN HSCs) for each group type.
- Perform one vs the rest DGEA between IL10 HSCs, IL10ra HSCs, and DN HSCs for each group type.
- Perform pairwise DGEA between IL10 HSCs, IL10ra HSCs, and DN HSCs for each group type.
- Perform GO analysis on upregulated and downregulated genes from the pairwise DGEA for each group type.
### All Cell Types tSNE
![image](https://user-images.githubusercontent.com/112181040/203364243-f5743e39-5a56-4b54-a2c0-5160615e5b39.png)
### All Cell Types UMAP
![image](https://user-images.githubusercontent.com/112181040/203364268-05ef6375-6a6a-4ffd-b075-7328f1aa8563.png)
### GSEA for Old Naive HSCs between IL10 HSCs, IL10ra HSCs, and DN HSCs (performed between each HSC group for each group type against several databases)
![image](https://user-images.githubusercontent.com/112181040/203365360-49b7d123-764f-48df-a007-e2b3cb237db7.png)
### Volcano Plof of Old Navie HSC Differentialy Expressed Gened (DEGs) between IL10ra HSCs and DN HSCs (performed between each HSC group for each group type)
![image](https://user-images.githubusercontent.com/112181040/203365886-14f3a93f-890d-4526-aee8-0931015ae2fd.png)
### GO Analysis of Old Naive HSC Upregulated DEGs between IL10ra HSCs and DN HSCs (performed between each HSC group for each group type)
![image](https://user-images.githubusercontent.com/112181040/203365918-60976e5a-7f60-4e4e-b29d-1aa504a94747.png)
### GO Analysis of Old Naive HSC Downregulated DEGs between IL10ra HSCs and DN HSCs (performed between each HSC group for each group type)
![image](https://user-images.githubusercontent.com/112181040/203366444-04841ef0-df31-46c7-8b31-666f02efa6c2.png)
