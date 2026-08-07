# snRNA-seq_ALCL
snRNA-seq analysis of ALCL


## 19. CytoSig
Preparing CytoSig input for RUN module:
- The expression values, from either RNASeq or MicroArray, should be transformed by log2(x+1), x could be FPKM, RPKM, or TPM for RNASeq. For single-cell RNASeq data, used log2(TPM/10 + 1). 
- Recommended to input differential profiles between the two conditions. 
- If data is from a sample collection without pairs, do mean-centralize the value of each gene across all samples.

Perform CytoSig RUN module:
- Log in to https://cytosig.ccr.cancer.gov/
- Choose RUN module
- Upload the input file (CytoSig_input_Endothelial_meancentered.txt) and click "Run"

