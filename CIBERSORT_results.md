CIBERSORT results
================
M. Behring
2017-09-04

-   [Main hypothesis](#main-hypothesis)
-   [Nodal Metastasis](#nodal-metastasis)

Main hypothesis
---------------

After meeting, we chose to not include cell type from CIBERSORT in analysis due to complexity in analysis and interpretation. Rather, we will analyze the relationship between RNA samples from our *signature* set of expression values from 22 different immune cell types (LM22), and our tumor *sample* sets of expression values for the same genes. [CIBERSORT](https://cibersort.stanford.edu/) uses permutation testing of the relationship between signature expression and sample expression. The null hypothesis is that there is no association between signature RNA and sample RNA expression. After 1000 permutations, all bulk tumor samples from patients having *p*-values of &lt;0.05 indicate an association with immune cells, and will be considered immune invasive.

It is the main hypothesis of this paper that individual genes from the LM22 signature will be deferentially expressed across the outcome of tumor invasiveness in some way that is consistent across three sets of breast tumor expression data. Our plan is to first identify which single genes have changes in expression in invasive tumors, and link them to cell types. Secondly, we will investigate the effect that molecular subtype and lymph node metastasis has upon this invasion-associated change of expression.

**Figure 1.** Genes with expression changes consistently associated with tumor immune invasivenss ![](CIBERSORT_results_files/figure-markdown_github/venn_all-1.png)

**Table 1.** Top 7 genes deferentially expressed in immune invasive tumors, in all patient populations

| Gene   |  Log Fold Change (METABRIC)|  Average Expression (METABRIC)|  FDR p-value (METABRIC)|  Log Fold Change (Zhao)|  Average Expression (Zhao)|  FDR p-value (Zhao)|  Log Fold Change (TCGA)|  Log Counts per Million (TCGA)|  FDR p-value (TCGA)|
|:-------|---------------------------:|------------------------------:|-----------------------:|-----------------------:|--------------------------:|-------------------:|-----------------------:|------------------------------:|-------------------:|
| CCL19  |                        2.00|                           7.79|                       0|                    1.64|                       1.91|                   0|                    1.18|                          10.91|                   0|
| CCL5   |                        1.58|                           9.98|                       0|                    1.30|                       1.49|                   0|                    1.08|                          12.33|                   0|
| CXCL10 |                        1.41|                          10.03|                       0|                    1.33|                       1.68|                   0|                    1.25|                          12.77|                   0|
| CXCL9  |                        2.06|                           8.79|                       0|                    2.98|                       2.36|                   0|                    1.81|                          13.67|                   0|
| GZMA   |                        1.47|                           7.94|                       0|                    1.13|                       1.42|                   0|                    1.09|                           9.52|                   0|
| GZMK   |                        1.90|                           8.27|                       0|                    1.16|                       1.44|                   0|                    1.20|                           9.68|                   0|
| MMP9   |                        1.01|                           7.96|                       0|                    1.26|                       1.70|                   0|                    1.54|                          13.90|                   0|

*This is output for an **adjusted** DE model using RNA expression values as dependent variable and three independent variables of: tumor invasiveness, nodal metastasis, and molecular subtype*

**Notes on Table 1 analysis:**
Main issue is that we are using LM22 as an outcome (invasiveness). We are also now evaluating the differential expression of genes that are, by definition, strongly linked to outcome. This explains why test *p*-values are so high.
\* First we used LM22 expression profiles to divide our tumor samples into two groups (from permutation test): invasive and non-invasive
\* Then we used the same ~500 genes to look at the differential expression between the very same groups!

In writing this up, I can say that there is some value in being able to pinpoint the exact genes which drive the invasive/non-invasive samples. This simplifies a test and allows for a 7 gene panel that probably would work as effectively as 500. Yet this logic still seems convoluted. Another selling point to this approach would be that we were actually able to do an adjusted DE test.Furthermore, if we are examining the modifying effect of NM and molecular subtype, we need to have some baseline measure of the relationship between expression across the two groups of invasive and non-invasive to start from.

Otherwise, understanding the individual contribution of each gene in subtypes makes sense. It is valuable to know if nodal metastasis is associated to reduced tumor invasiveness, then which genes are associated with increased tumor invasiveness in NM negative patients or vice versa (decreased tumor invasion in NM positives). A similar point can be made for molecular subtype. Again, the value would be in understanding how subtype status modifies the effect of genes associated with invasiveness in Table 1. If RNA-associated mechanisms of tumor innune invasion (or block) differ by molecular subtype, this is valueable from a biological point of view.

Nodal Metastasis
----------------

**Figure 2.** Genes with expression changes consistently associated with tumor immune invasivenss and node-negative status ![](CIBERSORT_results_files/figure-markdown_github/venn_NM-1.png)

**Table 2a.** Top 6 genes deferentially expressed in immune invasive tumors and node-negative status patients ( Zhao and TCGA overlap)

| Gene   |  Log Fold Change (Zhao)|  Average Expression (Zhao)|  p-value (Zhao)|  Log Fold Change (TCGA)|  Log Counts per Million (TCGA)|  p-value (TCGA)|
|:-------|-----------------------:|--------------------------:|---------------:|-----------------------:|------------------------------:|---------------:|
| CCL1   |                    0.05|                       0.99|            0.03|                    1.71|                           2.90|            0.00|
| CDHR1  |                    0.06|                       0.99|            0.02|                    1.33|                           7.34|            0.00|
| KLRD1  |                    0.10|                       1.03|            0.01|                    0.46|                           7.81|            0.01|
| PTGER2 |                    0.35|                       1.16|            0.01|                   -1.51|                           9.97|            0.00|
| TLR8   |                    0.05|                       1.01|            0.03|                    0.32|                           8.68|            0.04|
| TYR    |                    0.11|                       1.01|            0.04|                   -2.78|                           3.50|            0.00|

**Table 2b.** Top 6 genes deferentially expressed in immune invasive tumors and node-negative status patients ( METABRIC and TCGA overlap)

| Gene      |  Log Fold Change (METABRIC)|  Average Expression (METABRIC)|  p-value (METABRIC)|  Log Fold Change (TCGA)|  Log Counts per Million (TCGA)|  p-value (TCGA)|
|:----------|---------------------------:|------------------------------:|-------------------:|-----------------------:|------------------------------:|---------------:|
| ALOX15    |                        0.08|                           5.92|                0.04|                   -1.08|                           8.96|            0.00|
| CCL17     |                        0.14|                           5.77|                0.02|                    0.73|                           6.65|            0.01|
| CPA3      |                        0.84|                           9.48|                0.00|                   -1.08|                          11.28|            0.00|
| EFNA5     |                       -0.09|                           5.43|                0.01|                    0.74|                          11.91|            0.01|
| HIST1H2AE |                       -0.30|                           6.92|                0.05|                    0.75|                           9.87|            0.01|
| IL21      |                        0.07|                           5.45|                0.01|                    1.05|                           2.98|            0.02|
| LTC4S     |                        0.26|                           6.55|                0.01|                   -0.47|                           7.06|            0.03|
| MS4A2     |                        0.44|                           6.69|                0.00|                   -0.68|                           8.79|            0.01|
| ST8SIA1   |                       -0.14|                           6.09|                0.03|                    0.51|                           9.94|            0.03|
