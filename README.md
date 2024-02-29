# DeepFGRN: Inference of gene regulatory network with regulation type based on directed graph embedding

Here, we presents the datasets, trained models, and prediction results. In addition, we give the generation process of each figure in the paper to ensure reproducibility. 

The code and data are avaiable at https://github.com/PhoebeGaoZhen/DeepFGRN/tree/master.

In this manuscript, the Results section of DeepFGRN manuscript contains four figures (Fig.2-Fig.5) to demonstrate the performance of DeepFGRN model. (Fig. 1 is the overview of DeepFGRN framework)

## Fig.2 
This figure shows the comparison results of DeepFGRN model with existing state-of-the-art methods. a-b. Results of DeepFGRN compared with state-of-the-art methods for regular GRN reconstruction from bulk gene expression profiles. c. Prediction performance of DeepFGRN for regular GRN reconstruction on more datasets. d-h. Results of DeepFGRN compared with CNNGRN for FGRN reconstruction on nine datasets.

All the results of DeepFGRN (Fig.2a-h) can be reproduced via the data and code on GitHub repository: https://github.com/PhoebeGaoZhen/DeepFGRN/tree/master. It is recommended to follow the ***README.md*** in Github Repository to reproduce these results. The results of other existing methods (Fig.2a-b) are from their corresponding literature. The results of CNNGRN (Fig.2d-h) can be reproduced via ***CNNGRN_FGRN.zip*** according to ***README.md*** in Github Repository. 

After obtaining these results, we drew the figures using Origin and merged them together using Adobe Illustrator.


## Fig.3
This figure shows the effect of correlation analysis module on FGRN inference. a-e. Average results of ten times FCV for FGRN inference using different gene expression features.
Fig.3a-e are AUC, MCC, F1-score, Recall, and Precision under four scenarios, respectively. The four scenarios are 

(1) expCNN: only used onedimensional CNN to extract features of gene expression data.

(2) expResNet: only used one-dimensional ResNet (three residual blocks and one fully connected layer) to extract features of gene expression data. 

(3) Cnet: only utilized Cnet to extract correlation embedding between regulators and target genes. 

(4) expResNet+Cnet: jointly used onedimensional ResNet and Cnet. 

It should be noted that the above experiments do not use node bidirectional representation, and the flowchart of the above experiments can be seen in Fig. S2. 

The results can be reproduced via ***Fig3_experiments.zip***. Similarly, Origin and Adobe illustrator were adopted to plot Fig.3.
![image](https://github.com/PhoebeGaoZhen/Demo3/assets/54731874/daff07b4-fe0a-4ca9-822b-30cd58a3ad13)

## Fig.4
Fig.4 presents the effect of node bidirectional representation module on FGRN inference. 

Fig.4a-b. The out-degree and in-degree of prior FGRN of E.coli. 

Fig.4c-f. Average results of ten times FCV for FGRN inference using four features. The four features are 

(1) Cnet: only correlation embedding.

(2) expResNet+Cnet: both gene expression features learned via one-dimensional ResNet and correlation embedding. 

(3) Cnet+BLR: both correlation embedding and node bidirectional representation learned via node bidirectional representation module. 

(4) expResNet+Cnet+BLR: the combination of gene expression features, correlation embedding , and node bidirectional representation.

The results can be reproduced via ***Fig4c-f_experiments.zip***.

Fig.4g-l. Average results of ten times FCV for FGRN inference using features of neighbors in different directions.
To further demonstrate the influence of directivity for FGRN inference, we performed experiments on nine datasets where only the bidirectional representation of nodes differed, including 
(1) only Gs: only source neighbor representation, 
(2) only Gt: only target neighbor representation, 
(3) Gs+Gt: both source neighbor representation and target neighbor representation. 

The results can be reproduced via ***Fig4g-l_experiments.zip***.

## Fig.5 
Fig.5 shows Potential biomarkers and drugs analysis. a-d. Hub genes of four diseases based on MCC. e. The top ten potential drugs for breast cancer, liver cancer, lung cancer and COVID-19 based on DsigDB. f. Enrichment analysis of the first functional module of breast cancer.

To demonstrate the significance of FGRNs inference in human disease treatment clearly, we identified potential biomarkers and drugs for breast cancer, liver cancer, lung cancer and COVID-19, respectively. Specifically, a pre-trained model is obtained by training the DeepFGRN model using a balanced training set, which includes all prior gene pairs and the same number of unexplored gene pairs. Then, the remaining unexplored gene pairs were fed into the pre-trained DeepFGRN model to obtain the predicted scores. The above gene pairs were sorted in descending order according to their predicted scores. Next, a relatively complete FGRN which close to real was obtained via combining all prior gene pairs together with top N unexplored gene pairs. Subsequently, the visualization and bioinformatics analysis were conducted on this relatively complete FGRN. The results can be seen in the predictions compressed package in this directory.

Fig. 5a-d: We utilized cytoscape to visualize the relatively complete FGRN, then calculated MCC scores for four diseases through cytohubba. The top ten hub genes were obtained according to MCC scores. 

Fig. 5e: The Enrichr and DSigDB database were combined to identify candidate therapeutic drugs for four diseases based on above hub genes. The top ten candidate drug compounds according to p-value are shown in Fig. 5 e, and all results are shown in Supplementary Table. S8. 

Fig. 5f: We carried out enrichment analysis about functional modules, which obtained via MCODE, and the results are shown in Supplementary Table. S9. Since the genes in FGRNs with higher node centrality are more likely to participate in key biological processes15, we selected some important functional modules for enrichment analysis. Then, enrichment analysis based on GO, KEGG, Reactome and Wikipathway databases were conducted. The enrichment analysis results of the first functional module of breast cancer are shown in Fig. 5 f. Lastly, all other detailed results are shown in the Supplementary Fig. 5-8. 















