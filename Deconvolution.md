Tumor immune infiltrate deconvolution
================

Approach
--------

I used the [DeconRNASeq](http://bioconductor.org/packages/devel/bioc/html/DeconRNASeq.html) package to evaluate the non-tumor cell composition of samples in each of the three sets of patient RNA data: METABRIC, Zhao, et.al., and TCGA. While differential expression across case/control status will give relative measures of association through significant fold change, the use of an absolute measure of the difference between cases of nodal metastasis and controls who are metastasis free would provide additional information in understanding cell type level relationships in the data.
Required data inputs were:

**Dataset(s)**: Matrix of *m*-by-*n* expression values with *m* as the number of genes and *n* as the number of patient/tumor samples.

**Signature**: Matrix of *m*-by-*n* expression values with *m* as the number of genes which are cell type specific and *n* as the number of total immune cell types.

R code for deconvolution is as follows:

`BRIC_decon <- DeconRNASeq(X.df, sig_IRIS.df, checksig=TRUE,                           known.prop = FALSE, use.scale = TRUE, fig = FALSE)`

Results
-------

![](immunoediting/Deconvolution_files/ZHAO_deconv2.png) ![](immunoediting/Deconvolution_files/METABRIC_deconv2.png) ![](immunoediting/Deconvolution_files/TCGA_deconv2.png)
