# DeepFGRN: Inference of gene regulatory network with regulation type based on directed graph embedding

Here, we presents the datasets, trained models, and prediction results. In addition, we give the generation process of each figure in the paper to ensure reproducibility. 

The code and data are avaiable at https://github.com/PhoebeGaoZhen/DeepFGRN/tree/master.

In this manuscript, the Results section contains four figures (Fig.2-Fig.5) to demonstrate the performance of DeepFGRN model.

## Fig.2 
This figure show the comparison results of DeepFGRN model with existing state-of-the-art methods. a-b. Results of DeepFGRN compared with state-of-the-art methods for regular GRN reconstruction from bulk gene expression profiles. c. Prediction performance of DeepFGRN for regular GRN reconstruction on more datasets. d-h. Results of DeepFGRN compared with CNNGRN for FGRN reconstruction on nine datasets.

All the results of DeepFGRN (Fig.2a-h) can be reproduced via the data and code on GitHub repository: https://github.com/PhoebeGaoZhen/DeepFGRN/tree/master. It is recommended to follow the Readme on GitHub to reproduce these results. The results of other existing methods (Fig.2a-b) are from their corresponding literature. The results of CNNGRN (Fig.2d-h) can be reproduced via XXXXXXXXXXX(给出代码文件).
After obtaining these results, we drew the figures using Origin and merged them together using Adobe Illustrator.

# Fig.3
This figure show the effect of correlation analysis module on FGRN inference. a-e. Average results of ten times FCV for FGRN inference using different gene expression features.
Fig.3a-e are AUC, MCC, F1-score, Recall, and Precision under four scenarios, respectively. The four scenarios are 

(1) expCNN: only used onedimensional CNN to extract features of gene expression data.

(2) expResNet: only used one-dimensional ResNet (three residual blocks and one fully connected layer) to extract features of gene expression data. 

(3) Cnet: only utilized Cnet to extract correlation embedding between regulators and target genes. 

(4) expResNet+Cnet: jointly used onedimensional ResNet and Cnet. 

It should be noted that the above experiments do not use node bidirectional representation, and the flowchart of the above experiments can be seen in Fig. S2. 

The results can be reproduced via XXXXXXXXXX代码文件. Similarly, Origin and Adobe illustrator were adopted to plot Fig.3.

## Fig.4
Fig.4 presents the effect of node bidirectional representation module on FGRN inference. 

Fig.4a-b. The out-degree and in-degree of prior FGRN of E.coli. 

Fig.4c-f. Average results of ten times FCV for FGRN inference using four features. 

Fig.4g-l. Average results of ten times FCV for FGRN inference using features of neighbors in different
directions.



















