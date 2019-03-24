# Intro of BIDS

BIDS follows simple but carefully defined terminology.

Filenames are organized with a series of key-values and end with a file type, where keys and file types are predefined and values are chosen by the user. Some rules are mandatory, some rules are optional.

BIDS provides data dictionaries and strict naming conventions for normative naming.

BIDS can be used to describe most datasets, however, there are some cases that do not fit the current version of BIDS. Therefore, in these cases, one can include additional files and sub-dirs to the existing dir structure following common sense and general naming guidelines.

BIDS is designed to standarize and describe raw data. In this standard, derived data from the raw should be kept separate from the raw data, which can not only make it easy to distinguish between the raw and the derive, but also can prevent raw data from being changed.

There are 4 levels in BIDS, they are (in hierarchical order) MRI acquisition, session, subject, and dataset. Any metadata can be defined at one of them. Additionally, it is noteworthy that there is an inheritance principle for this standard -- values from the superior will be inherited and used by the subordinate, unless they are overwritten by the files from the subordinate.

## References
1. KJ Gorgolewski et al.: *The brain imaging data structure, a format for organizing and describing outputs of neuroimaging experiments*. In 2016.