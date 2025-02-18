![alt text](https://secureservercdn.net/198.71.233.106/h9j.d46.myftpupload.com/wp-content/uploads/2019/09/palmerlab-logo.png)
![alt text](https://ratgenes.org/wp-content/uploads/2014/11/GWAS_1200x150pxBanner-01.png)
# HPC
## Source code for HS rats pipeline on HPC
:information_source: :information_source: :information_source:  **INFOMATION** :information_source: :information_source: :information_source:    
This folder contains the complete pipeline code that utilizes HPC's different schedulers' array jobs feature to achieve parallelization. You may want to visit the pipeline flow [here](https://github.com/Palmer-Lab-UCSD/HS-Rats-Genotyping-Pipeline/blob/main/assets/HS_Rats_Lc-WGS_Genotyping_Pipeline_Design.pdf).

## Contents
**[submission_TSCC_PBS.sh](submission_TSCC_PBS.sh)**  
Submission script for the pipeline on  [TSCC](https://www.sdsc.edu/support/user_guides/tscc.html). You may want to change this file accordingly if you are running this pipeline on a different HPC system.  

**[pipeline_arguments](pipeline_arguments)**  
Pipeline arguments.  
Line 1: Flow cell directory  
Line 2: Flow cell metadata
Line 3: Sequencing data directory  
Line 4: Reference genome  
Line 5: Reference panels for STITCH  
Line 6: Directory where you keep the code for the pipeline  

**[previous_flow_cells_metadata](previous_flow_cells_metadata)**  
Paths to previous flow cells' metadata.  

**[previous_flow_cells_bams](previous_flow_cells_bams)**  
Paths to previous flow cells' BAM files.   

## Documentation  
### Before running the pipeline:
Please update the following files to suit your purpose:  
1. Follow the instruction in [software](software) to install required software
2. [pipeline_arguments](pipeline_arguments)
3. [previous_flow_cells_metadata](previous_flow_cells_metadata)
4. [previous_flow_cells_bams](previous_flow_cells_bams)
5. Update the PBS Torque arguments and the corresponding file locations on [submission_TSCC_PBS.sh](submission_TSCC_PBS.sh).  

### Run the pipeline on TSCC:
To run the pipeline on other PBS platform besides TSCC, please change the submission script accordingly.
1. Change the permission of the submission script
```
chmod u+x submission_TSCC_PBS.sh
```
2. Run the submission script
```
./submission_TSCC_PBS.sh
```  
