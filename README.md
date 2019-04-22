# ActflowToolbox
## The Brain Activity Flow ("Actflow") Toolbox

## Overview
The purpose of this software package is to facilitate use of neuroscience methods linking connectivity with cognitive/behavioral functions and task-evoked activity. The primary focus is on _activity flow mapping_ (http://rdcu.be/kOJq) and related methods such as _information transfer mapping_ (http://rdcu.be/wQ1M).

Other included methods that can be used along with activity flow mapping (or not) include advanced versions of task-state functional connectivity, resting-state functional connectivity, and general linear modeling (multiple regression). Supporting methods such as preprocessing and simulations for validation are also included. The primary focus is on fMRI data, but in principle these approaches can be applied to other kinds of data.

## How to install

git clone --recurse-submodules https://github.com/ColeLab/ActflowToolbox.git

### Included connectivity-activity mapping methods
* Activity flow mapping (http://rdcu.be/kOJq)
* Information transfer mapping (http://rdcu.be/wQ1M)

### Included connectivity mapping methods
* _All methods can be applied to resting-state or task-state data_
* Correlation-based functional connectivity
* Multiple regression and partial correlation function connectivity
	* Multiple regression connectivity
	* Regularized multiple regression connectivity
		* Principle components regression connectivity (PCR)
	* Partial correlation
	* Regularized partial correlation
* Special preprocessing for task-state functional connectivity
	* Flexible mean task-evoked response removal (http://www.colelab.org/pubs/ColeEtAl2019NeuroImage.pdf)
* Causal connectivity (fGES; https://doi.org/10.1007/s41060-016-0032-z)

## Conventions
* Data matrices all node X time
* Directed connectivity matrices all source X target
* Primary (default) brain parcellation: CAB-NP (https://github.com/ColeLab/ColeAnticevicNetPartition), which uses the Glasser2016 parcellation for cortex (https://balsa.wustl.edu/study/show/RVVG)

## Software development guidelines
* Primary language: Python 3
* Secondary language (for select functions, minimally maintained/updated): MATLAB
* Versioning guidelines: Semantic Versioning 2.0.0 (https://semver.org/); used loosely prior to v1.0, strictly after
* Style specifications:
	* Tabs for indentations (benefit: less chance for errors, e.g., 3 spaces instead of 4 for indentation)
	* Use intuitive variable and function names
	* Add detailed comments to explain what code does (especially when not obvious)

## Contents
* _Directory_: actflowcalc - Calculating activity flow mapping
	* parcelwise_noncircular_surface.py: High-level function for calculating parcelwise actflow with parcels that are touching (e.g., the Glasser 2016 parcellation). This can create circularity in the actflow predictions due to spatial autocorrelation. This function excludes vertices within 10 mm of each to-be-predicted parcel.
* _Directory_: connectivity_estimation - Connectivity estimation methods
* _Directory_: dependencies - Other packages Actflow Toolbox depends on
* _Directory_: infotransfermapping - Calculating information transfer mapping
* _Directory_: matlab_code - Limited functions for activity flow mapping in MATLAB
* _Directory_: network_definitions - Data supporting parcel/region sets and network definitions
* _Directory_: pipelines - Example pipelines for data analyses
* _Directory_: preprocessing - Functions for preprocessing (after "minimal" preprocessing)
* _Directory_: simulations - Simulations used for validating methods
* _Directory_: tools - Miscellaneous tools
