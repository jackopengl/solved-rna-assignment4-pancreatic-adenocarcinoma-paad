Download Link: https://assignmentchef.com/product/solved-rna-assignment4-pancreatic-adenocarcinoma-paad
<br>
<a href="https://en.wikipedia.org/wiki/Pancreatic_cancer">Pancreatic</a> <a href="https://en.wikipedia.org/wiki/Pancreatic_cancer">Adenocarcinoma</a> <a href="https://en.wikipedia.org/wiki/Pancreatic_cancer">(PAAD)</a> is the third most common cause of death from cancer, with an overall 5-year survival rate of less than 5%, and is predicted to become the second leading cause of cancer mortality in the United States by 2030.

Ribonucleic acid (<a href="https://en.wikipedia.org/wiki/RNA">RN</a>​ <a href="https://en.wikipedia.org/wiki/RNA">A</a><a href="https://en.wikipedia.org/wiki/RNA">)</a><u>​</u> is a polymeric molecule essential in various biological roles in coding, decoding, regulation and expression of genes. RNA and DNA are nucleic acids, and, along with lipids, proteins and carbohydrates, constitute the four major macromolecules essential for all known forms of life.

<a href="https://bitesizebio.com/13542/what-everyone-should-know-about-rna-seq/">RNA-Seq</a> (RNA sequencing), is a sequencing technique to detect the quantity of RNA in a biological sample at a given moment. Here we have a<strong> dataset of normalized RNA Sequencing reads for pancreatic cancer tumors</strong>.​ The measurement consists of ~20,000 genes for 185 pancreatic cancer tumors. The file format is <a href="http://software.broadinstitute.org/cancer/software/genepattern/file-formats-guide#GCT">GC</a><u>​ </u><a href="http://software.broadinstitute.org/cancer/software/genepattern/file-formats-guide#GCT">T</a> , a tab-delimited file used for sharing gene expression data and metadata (details for each sample) for samples.

<ul>

 <li>The R package <a href="https://github.com/cmap/cmapR">cmap</a>​ <a href="https://github.com/cmap/cmapR">R</a> can be used for reading GCTs in R.​</li>

 <li>The python package <a href="https://pypi.org/project/cmapPy/">cmapP</a>​ <a href="https://pypi.org/project/cmapPy/">y</a> can be used for reading GCTs in python.​</li>

 <li><a href="https://artyomovlab.wustl.edu/phantasus/">Phantasus</a> is an open source tool which is used to visualise GCT files, make various plots, apply algorithms like clustering and PCA among others.</li>

</ul>

<h2>1.Data cleaning and check the distribution of gene expression across samples</h2>

<ul>

 <li>Remove genes with NaNs. How many genes had NaNs?</li>

 <li>Generate gene expression distribution for all samples. How is the distribution of gene expression across samples?</li>

</ul>

<h2>2. Identify only the <a href="https://en.wikipedia.org/wiki/Pancreatic_cancer#Exocrine_cancers">Exocrin</a>​ <a href="https://en.wikipedia.org/wiki/Pancreatic_cancer#Exocrine_cancers">e</a> <u>​ </u>(adenocarcinoma) tumors and remove <a href="https://en.wikipedia.org/wiki/Pancreatic_cancer#Neuroendocrine">Neuroendocrin</a><u>​ </u><a href="https://en.wikipedia.org/wiki/Pancreatic_cancer#Neuroendocrine">e</a> tumors.​</h2>




We want to stratify these tumor samples by the type of pancreatic cancer they exhibit. For this, apply dimensionality reduction techniques (PCA) to find these two groups within this multi-dimensional data.




<ul>

 <li>Visualize the data whole data using PCA. (<em>Use</em>​<em> python or R to generate the PCA plots. You may use </em><a href="https://artyomovlab.wustl.edu/phantasus/">​</a><a href="https://artyomovlab.wustl.edu/phantasus/"><em>Phantasus</em></a><a href="https://artyomovlab.wustl.edu/phantasus/">​</a> <em>for validation</em>​)</li>

 <li>What does the analysis say about the general behaviour of the different samples?</li>

 <li>Are the neuroendocrine tumors clearly separable from the adenocarcinoma tumors?– Overlay the information from metadata column<em> ‘histological_type_other’</em> on top of PCA plot and check if neuroendocrine tumors are separating out.</li>

 <li>What can be said about the variance of the PCA?</li>

 <li>Which features contribute the most in PC1, PC2 and so on? Can you come up with an appropriate visualization to demonstrate the feature relevance for these PC components?</li>

 <li>Remove the neuroendocrine tumors from the dataset so that it contains only the adenocarcinoma tumor samples. The histology for the different tumor samples is contained in the GCT file.</li>

</ul>




Here are pointers on this exercise:  <a href="https://bioconductor.org/packages/release/bioc/html/pcaExplorer.html">pcaExplore</a>​ <a href="https://bioconductor.org/packages/release/bioc/html/pcaExplorer.html">r</a> <u>​ </u>, <a href="https://artyomovlab.wustl.edu/phantasus/phantasus-tutorial.html">Phantasus tutoria</a><u>​    </u><a href="https://artyomovlab.wustl.edu/phantasus/phantasus-tutorial.html">l</a>







<h2>3.  ​ Understand the effect of Interferons in Pancreatic Adenocarcinoma​</h2>




<a href="https://en.wikipedia.org/wiki/Interferon">Interferons</a> (IFNs) are a group of signaling proteins made and released by host cells in response to the presence of several pathogens, such as viruses, bacteria, parasites, and also tumor cells. Type I interferons (IFNs) are a large subgroup of interferon proteins that help regulate the activity of the immune system. The genes responsible for type 1 Interferons is called <a href="https://en.wikipedia.org/wiki/Interferon_type_I">Typ</a>​ <a href="https://en.wikipedia.org/wiki/Interferon_type_I">e</a> <a href="https://en.wikipedia.org/wiki/Interferon_type_I">1</a> <a href="https://en.wikipedia.org/wiki/Interferon_type_I">IFN</a> <a href="https://en.wikipedia.org/wiki/Interferon_type_I">signature</a> and consists of a set of 25 genes in homo sapiens.

<ul>

 <li>Can you plot the gene expression values for these genes for pancreatic adenocarcinoma?</li>

 <li>Run the GSVA (a single sample gene set enrichment) algorithm with 25 gene IFN signature as the gene set and the subsetted pancreatic cancer data as the expression dataset. (Suggested tools: Use <a href="https://bioconductor.org/packages/release/bioc/html/GSVA.html">GSV</a>​ <a href="https://bioconductor.org/packages/release/bioc/html/GSVA.html">A</a> <a href="https://bioconductor.org/packages/release/bioc/html/GSVA.html">package</a>)​ Additional links: ​ <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-14-7">GSVA</a> <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-14-7">paper</a><a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-14-7">,</a><u>​</u> <a href="http://clincancerres.aacrjournals.org/content/23/12/3129">A</a><u>​</u> <a href="http://clincancerres.aacrjournals.org/content/23/12/3129">paper</a> <a href="http://clincancerres.aacrjournals.org/content/23/12/3129">for</a> <a href="http://clincancerres.aacrjournals.org/content/23/12/3129">reference</a> <a href="http://clincancerres.aacrjournals.org/content/23/12/3129">which studies T-cell signature in PAAD</a>)​</li>

 <li>Check distribution of GSVA scores for samples. Do the GSVA scores segregate samples into subtypes?</li>

</ul>

<strong> </strong>

<strong>Installation Hacks: </strong>

<ul>

 <li>Running GSVA in R: In case there are dependencies issues, install GSVA inside rstudio docker container: <a href="https://hub.docker.com/r/rocker/rstudio/">https://hub.docker.com/r/rocker/rstudio</a><u>​      </u><a href="https://hub.docker.com/r/rocker/rstudio/">/</a></li>

 <li>Running GSVA in Python: Run GSVA through the docker given for gsva python <a href="https://github.com/jason-weirather/GSVA">https://github.com/jason-weirather/GSVA</a><a href="https://github.com/jason-weirather/GSVA">,</a><u>​</u> <a href="https://hub.docker.com/r/vacation/gsva">https://hub.docker.com/r/vacation/gsv</a>​ <a href="https://hub.docker.com/r/vacation/gsva">a</a></li>

</ul>

<h2>4.  ​ Unsupervised analysis​</h2>

<strong> </strong>

Do unsupervised clustering on the gene expression data with the algorithm of your choice and identify any correlations of the clusters so formed with the sample metadata. What statistical tests do you recommend to test the strength of association between the identified clusters and the various sample metadata? Come up with appropriate visualizations.




Note: <em>Don’t</em>​<em> ignore the theoretical questions as they have weightage as well. Try to answer them in the notebook itself. </em>