# snRNA-seq_ALCL
snRNA-seq analysis of ALCL

## 17. Compass
Compass is one of the metabolism analysis tools. 
Documentation: `https://compass-sc.readthedocs.io/en/latest/installation.html`
Preparing Compass input: 
- The original Compass uses Scanpy and other Python-based tools for pseudobulking, but here I use AggregateExpression in Seurat to do pseudobulking. 
- The key is to make sure the output files are in the format that Compass expects (expression.mtx, genes.tsv, sample_names.tsv, and metadata).

Perform Compass:
- download Gurobi license on `https://license.gurobi.com/manager/licenses/` and make sure it's in the same dir as your input files and sbatch script

Analysis:
- Compass result analysis is available on `https://compass-wagnerlab.readthedocs.io/en/latest/` 
- But here we generate a heatmap and rank the pathway enrichment result by combining Compass result (reactions.tsv) and GSEA


## 19. CytoSig
Preparing CytoSig input for RUN module:
- The expression values, from either RNASeq or MicroArray, should be transformed by log2(x+1), x could be FPKM, RPKM, or TPM for RNASeq. For single-cell RNASeq data, used log2(TPM/10 + 1). 
- Recommended to input differential profiles between the two conditions. 
- If data is from a sample collection without pairs, do mean-centralize the value of each gene across all samples.

Perform CytoSig RUN module:
- Log in to https://cytosig.ccr.cancer.gov/
- Choose RUN module
- Upload the input file (CytoSig_input_Endothelial_meancentered.txt) and click "Run"

