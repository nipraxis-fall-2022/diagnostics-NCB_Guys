# Diagnostics project

Script go in the `scripts` directory.

Library code (such as Python modules or packages) goes in the `packages` directory.

You should put this `packages` directory on your Python PATH.

This file has instructions on how to get, validate and process the data.

## Get the data

    cd data
    curl -LO http://nipy.bic.berkeley.edu/psych-214/group00.tar.gz
    tar zxvf group00.tar.gz
    cd ..

## Check the data

    python3 scripts/validate_data.py data

## Find outliers

    python3 scripts/find_outliers.py data

This should print output to the terminal of form:

    <filename> <outlier_index>, <outlier_index>, ...
    <filename> <outlier_index>, <outlier_index>, ...

Where `<filename>` is the name of the image that has outlier scans, and
`<outlier_index>` is an index to the volume in the 4D image that you have
indentified as an outlier.  0 refers to the first volume.  For example:

    group00_sub01_run1.nii 3, 21, 22, 104
    group00_sub02_run2.nii 11, 33 91
    group00_sub04_run2.nii 101, 102, 132
    group00_sub07_run2.nii 0, 1, 2, 166, 167
    group00_sub09_run2.nii 3
