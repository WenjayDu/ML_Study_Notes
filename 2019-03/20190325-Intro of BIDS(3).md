# Intro of BIDS

There are some specified file formats in BIDS(V1.0.0).

| type | format |
-------|--------
|image files| NIfTI(.nii) |
|tabular files|TSV(.tsv)|
|Key/value files (dictionaries)|JSON(.json)|

There are also required, recommended and optional metadata in BIDS.

Although current version of BIDS choose NIfTI to store neuroimaging data due to its popularity, but other file formats like MINC also used widely. Therefore, different flavors of BIDS can be designed to support these formats.

To create a BIDS compatible dataset, we can take following steps👇

**Step 1: Convert DICOM files to NIfTI.** 

* use a DICOM to NIfTI converter such as dcm2niix

**Step 2: Create folder structure, rename and copy NIfTI files.**

* create structural folders to describe and organize dataset

**Step 3: Add remaining data.**

* provide details of the experimental paradigm for the task fMRI data

**Step 4: Add missing metadata.** 

* like providing the name of each fMRI task
* Optionally, we can add information about task instructions and description. 
* create a dataset_description.json file with fields that include the name and description of the dataset as well as the version of BIDS standard used

**Step 5: Validate the dataset.** 

* use the BIDS Validator to check if any of the required or recommended metadata are missing


## References
1. KJ Gorgolewski et al.: *The brain imaging data structure, a format for organizing and describing outputs of neuroimaging experiments*. In 2016.