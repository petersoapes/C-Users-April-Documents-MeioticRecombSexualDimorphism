#README

This repo contains manuscript file, supplemental figures and Tables, analysis scripts and data files. Cell image files for this analysis are hosted on NSF CyVerse https://www.cyverse.org/ and can be shared on request.

File List and brief discriptions
File_S1.xlsx: MLH1 data
File_S2.xlsx: Chromosome class proportions
File_S3.xlsx: DMC1 data
File_S4.xlsx: Total SC data
File_S5.xlsx: Curated Bivalent Data
File_S6.Rmd: Script for setting up data
File_S7.RData: Cleaned Data
File_S8.Rmd: Analysis Script
File_S9.RData: Analysis and Results RData  
File_S10.R: Commonly used Functions

-------------------------------------------

Additional Details

File_S1.xlsx / MLH1.AnonData_formated.xlsx:
Batch - I quantified MLH1 counts by anonymizing file names and pooling in manageable batch sizes (by sex, since that can't be anonymized).
Quality, 1(best) to 5(worst), 
n (number of bivalents, including XY in males).
nMLH1.foci  - doesn't include MLH1 on XY
achiasmate - number of bivalents without a CO.
asynapsis - number of bivalents with partial areas of incomplete synapsis.
REDO.crop - this was to keep track of if there was extra SC noise in the image. I had plans to go back and clean up all the images, but it was taking too much time.

File_S2.xlsx / ChrmClass_Proportions.xlsx
Sheet1: raw data of chromosome classes per cell from DNACrossOver data.
Sheet2: propotions of classes compiled by strain.

File_S3.xlsx / DMC1_data.xlsx:  
'bars' & 'left.over' columns refer to my annotated counting, marking 20 and 1 foci respectively.

File_S4.xlsx / Total.SC_DF_5.31.20.xlsx:
This is the merged MLH1 file and total SC measures from Richard Wang's python script.
bin_size; 'binary size', total area after turning red channel binary.
skel_size; 'skeleton size',  Sum of single pixel wide trace of bivalents.


File_S5.xlsx / Curated_BivData_5.30.20.xlsx:
These are notes from the curation process of confirming the accuracy of the values and trace image produced by DNACrossOver software. The outputs show what the algorithm segmented as single objects from the whole cell image in indexed boxes.
ChromosomeLength - length of single SC.
boxNumber - Indexed box number for a single bivalent object.
Obj.ID - Unique ID for each object (fileName_boxnumber).
SC.pass - If the object segments well, '1'. '0' otherwise. 
Foci.pass - If foci were segmented correctly '1', all 'real' foci ones and no extras. Note there are ~230 bivalents where the segmentation of bivalent shape is good, but foci didn't clearly pass. These were excluded from the paper analysis.

File_S6.Rmd / MLH1_data_setup_10.11.20.Rmd
Script for cleaning data and setting up dataframes for analysis.

File_S7.RData / Data.RData 
R Data file after data cleaning scripts were run.

File_S8.Rmd / Results_setup.Rmd
Script for running analyses.

File_S9.RData / Results_setup_10.11.20.RData
R Data file after analysis scripts were run.

File_S10.R / CommonFunc_MLH1repo.R
Functions used for adding varibles based on image name. Image naming logic: (dateImaged_dateDissected_strain_sexMouse#_slide_image#_rev)