# Biologist 1: Jona

---

## Paper 1 ❌
### **Identifying Drug Targets for Neurological and Psychiatric Disease via Genetics and the Brain Transcriptome**

**Paper Link:**  
https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1009224  

**Summary:**  
This 2021 paper uses Mendelian randomization (MR) and colocalization analysis to identify potential drug targets for neurological and psychiatric diseases by linking brain gene expression to disease risk.

**Methodology:**  
Combined two-sample MR (to establish causal relationships) with Bayesian colocalization (to confirm shared genetic variants) using brain-specific expression data rather than blood proxies.

**GitHub Link:**  
https://github.com/denisbrd/braineQTLMR_datasets/tree/v1.01  

**Notes:**  
- Code is **not accessible**, which may limit reproducibility or use in our project. 

---

## Paper 2 ❌  
### **Using the Structure of Genome Data in the Design of Deep Neural Networks for Predicting ALS from Genotype**

**Paper Link:**  
https://academic.oup.com/bioinformatics/article/35/14/i538/5529261  

**Summary:**  
This paper uses deep learning to identify disease-associated genetic variants in regulatory regions that may be linked to amyotrophic lateral sclerosis (ALS).

**GitHub Link:**  
https://github.com/byin-cwi/ALS-Deeplearning  

**Notes:**  
- The code is feasible for our project.  
- Fully written in Python; files are not very long.  
- Uses tools from lectures (**pandas**, **numpy**, **PyTorch**, **scikit-learn**).  
- May be useful for learning how these tools analyze biological data.  
- Some uncertainty if the included text file is the correct dataset for running the code.

---

## Paper 3 ❌
### **Prediction of Alzheimer's Disease Based on Deep Neural Network Integrating Gene Expression and DNA Methylation**

**Paper Link:**  
https://www.sciencedirect.com/science/article/pii/S0957417419305834  

**Summary:**  
This paper integrates genomic data and DNA methylation features to build a model predicting Alzheimer’s disease.

**GitHub Link:**  
https://github.com/ChihyunPark/DNN_for_ADprediction  

**Notes:**  
- Code is mostly Python, with a little R.  
- Prediction model is not overly complicated.  
- Large datasets may make the pipeline slow to run.  

---

## Paper 4 ❌
### **Towards Personalized Medicine in Cystic Fibrosis : Patient-Specific Modeling of Mucociliary Clearance Using Physiologically-Based Flow Constraints**

**Paper Link:**
https://www.proquest.com/docview/3132883329/fulltextPDF/72D991F7FC2349E8PQ/1?accountid=10932&sourcetype=Dissertations%20&%20Theses

**Summary:**
This paper creates a model to make mucus-clearing treatment for cystic 
fibrosis more personalized, taking into account variablilty in lung 
regions.
   
**GitHub Link:**
https://github.com/monshap/psanalysis/tree/master
- Sample Images are located uner "tests" 

**Notes:**
- The code seems feasible for the project. 
- It is entirely in Python
- Uses libraries such as NumPy 
- The paper is long as it is a PhD manuscript but this also means that 
there is a lot of explanation for what the different parts of the code is 
used for. 
- The appendix walks you through the code
- The sample data provided is used only to validate that the program works not to provide any 
information

---

## Paper 5 ❌
### **Using genomic data and machine learning to predict antibiotic resistance: A tutorial paper**

**Paper Link**
https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1012579

**Summary**
The paper is a tutorial guiding how to apply machine learning (ML) on bacterial genomic data to predict antibiotic resistance (phenotype). It focuses on data from many 
isolates of Escherichia coli (E. coli), with known resistance/susceptibility profiles against a panel of antibiotics, and corresponding genomic data.

**GitHub Link**
https://github.com/Lucy-Moctezuma/ML-Tutorial-for-Antibiotic-Resistance-Predictions-for-E.-Coli

**Notes**
- This code seems feasible. 
- The code is written in Colab which makes it easily reproducible
- Uses common prediction models and is meant to be for beginners so might be easier to implement 
- This paper is a tutorial paper, it takes data from a study that is cited in the paper 
- The data provides is preprocessed
- Most of the notebooks ran successfully 
- Some minor issues regarding out-dates versions of library features
- Could not get the 5th and 6th notebook to run but it seemed more like an  issue with using Google 
Drive than with the code


--

## Paper 6 ❌
### **Modeling functional cell types in spike train data**

**Paper Link**
https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1011509

**Summary**
This paper introduces a statistical method to identify functional cell types directly from neural spike-train data. Instead of classifying neurons based on anatomy or gene 
expression, the method groups neurons by the similarity in their firing behavior.They use a hierarchical model where each cell type defines distributions over GLM parameters 
for neurons, and they fit everything jointly using a variational EM algorithm.

**GitHub Link**
https://github.com/zdeblick/ClusteredGLMs

**Notes**
- Code seems very feasible a it uses basic Python coding 
- The paper describes hyperparameters explicitly
- The authors provide details about how they structured the GLM
- Takes entirely too long to run

---

## Paper 7 ❌
### **A computational approach to study age-related modifications of the genes involved in Parkinson's disease**

**Paper Link**
https://www.sciencedirect.com/science/article/pii/S0010482525011163

**Summary** 
The paper titled “A computational approach to study age-related …” (2025) uses network analysis and pathway‐enrichment analysis to examine how gene–gene interactions and 
biological pathways shift in an age-dependent manner. Rather than focusing on single genes, the authors build a gene-expression network (or networks), then identify modules 
or subnetworks that show changes with age; these modules map to biological processes or pathways.

**GitHub Link**
https://github.com/mmilano87/tegena

**Notes**
- most of the computational workflow in that paper can be reproduced using Python
- Output generated was incomplete, could not figure out was missing from the code 

---

## Paper 8 - SUCCESS!
### **Persistent Interruption in Parvalbumin-Positive Inhibitory Interneurons: Biophysical and Mathematical Mechanisms**

**Paper Link**
https://www.eneuro.org/content/11/7/ENEURO.0190-24.2024/tab-e-letters - download pdf

**Summary**
The study shows that in hippocampal CA1, fast-spiking interneurons that express the protein parvalbumin (PV-INs) exhibit “type 2” excitability. Using mathematical modeling 
and biophysical analysis, the authors demonstrate that a slowly inactivating potassium current (via the channel KV1) can produce robust, persistent interruption of firing in 
these PV-INs — meaning after an inhibitory input, the interneuron can remain silent for an extended time before resuming firing.

**GitHub Link**
https://github.com/ModelDBRepository/2016658

**Notes**
- The core results come from computational modeling, not difficult lab experiments.
- Biophysical neuron models are well-established — many exist already with PV-interneuron properties and KV1 channels.

