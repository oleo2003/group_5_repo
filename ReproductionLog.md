# Paper Reproduction Log - Engineer 1: Liv Lanford

This document tracks all papers we have actually tried to reproduce: what we ran, what broke, and what worked.

# Biologist 1's papers: Jona

### Paper 1 – Identifying Drug Targets for Neurological and Psychiatric Disease via Genetics and the Brain Transcriptome

- **Link to paper**: https://journals.plos.org/plosgenetics/article?id=10.1371/journal.pgen.1009224
- **Code repo**: https://github.com/denisbrd/braineQTLMR_datasets/tree/v1.01  

**What we tried**

- Looked for solid README file to explain the datasets and how to run
- Looked for outline of the tools and platforms

**What went wrong**

- only see the extensive datasets used, not the core code that makes up their pipeline

**Conclusion**
- Will not run/discard -> can't reproduce without code


### Paper 2 - Using the Structure of Genome Data in the Design of Deep Neural Networks for Predicting ALS from Genotype

- **Link to paper**: https://academic.oup.com/bioinformatics/article/35/14/i538/5529261
- **Code repo**: https://github.com/byin-cwi/ALS-Deeplearning

**What we tried**

- Downloaded all files onto Desktop (copy raw data, "git clone [paste link]") 
- looked through the pipeline and found needed files: link to sample data, all code to run, README instructions

**What went wrong**

- The link to the sample data is expired, can't find access to data. 

**Conclusion**
- Discard paper -> can't reproduce without data

## Paper 3 - Prediction of Alzheimer's Disease Based on Deep Neural Network Integrating Gene Expression and DNA Methylation

- **Link to paper**: https://www.sciencedirect.com/science/article/pii/S0957417419305834
- **Code repo**: https://github.com/ChihyunPark/DNN_for_ADprediction

**What we tried**

- checked all content is there: compile steps, code, data
- Used Docker to contain the specific tools needed:
	- python 3.5
	- numpy 1.16.3
	- pandas 0.24.2
	- scikit-learn 0.21.0
	- tensorflow 1.4.1
		
	***How:*** 
		- nano Dockerfile
		- inside file: 
 
			FROM tensorflow/tensorflow:1.5.0-py3

			ENV DEBIAN_FRONTEND=noninteractive

			# Upgrade pip a bit (but not too new to break old stuff)
			RUN python -m pip install --upgrade \
    			pip==20.3.4 \
    			setuptools \
    			wheel

			# Install / pin the rest of the Python deps
			# We **do not** specify scipy here – it already comes with the TF image.
			RUN pip install --no-cache-dir \
    			numpy==1.16.3 \
    			pandas==0.24.2 \
    			scikit-learn==0.20.4

			WORKDIR /workspace
	 
- tried running all files 
- started editing files for better run 

**what went wrong**
- errors with the processing step -> realized the data is already processed, only need to split the data into training and test. 
- got stuck at the hyperparameter step -> the Bayesian modelling file had some errors. I added this code snippet to fix it:
		In function “applyDimReduction…” I added these lines:
			# Load full methylation dataframe
 			xy_all_df = pd.read_csv(infilename, sep="\t")

 			# Keep only CpGs that actually exist in the file
  			existing_cols = set(xy_all_df.columns)
 			selected_cpglist = [c for c in selected_cpglist if c in existing_cols]

   			# Now it's safe to subset
   			xy_sel_df = xy_all_df[selected_cpglist]
- With edits, the command "python [bayesian model file name]" runs... but takes many hours because it is training multiple deep networks
	*I am worried about how heavy this is on my Mac to run

**Conclusion**
- Keep trying to run, but look for other papers as well
- update: gave up running; would try on cluster but takes a few weeks to set up...


## Paper 4 - Towards Personalized Medicine in Cystic Fibrosis : Patient-Specific Modeling of Mucociliary Clearance Using Physiologically-Based Flow Constraints
- ** Link to paper **:  https://www.proquest.com/docview/3132883329/fulltextPDF/72D991F7FC2349E8PQ/1?accountid=10932&sourcetype=Dissertations%20&%20Theses
- ** Code Link **:https://github.com/monshap/psanalysis/tree/master
**What we tried**
- downloaded repo from git hub using "git clone"
- followed the directions written in the thesis to download the psanalysis tool they created.
- ran code smoothly on the sample data provided but no set output...
- to see if anything happened, i generated my own graphs:
- these demonstrated that the program worked to take in 2D planar gamma scintigraphy images of patients and then parse into a matrix for analysis. However, the sample data given cannot recreate the study's findings that hypertonic saline therapy improves mucociliary clearance (MCC) in the lungs. It only shows that the matrix accurately portrays mucus transport and ventilation in the lungs TO BE analyzed. Teh actual data used in the study is sensitive patient information = unaccesible.  

**Conclusion**
- not ideal because we can't reproduce their findings
- good fall back because we did validate their mucus tracking program! 
