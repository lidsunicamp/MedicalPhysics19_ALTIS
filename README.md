# ALTIS - Automatic Lungs and Trachea Image Segmentation

Repository with useful material for the paper: Azael Sousa et al., "**ALTIS: A Fast and Automatic Lung and Trachea CT-Image Segmentation Method**", Medical Physics Journal 2019.

We propose a method called ALTIS that uses only image processing operators based on optimum connectivity to segment the volume of air of both lungs and trachea separately in CT images of the thorax.

## Materials

ALTIS has been evaluated in a large set of CT images gathered from different public datasets. For each dataset, the gold-standard used in the experiments is provided in the `nii.gz` format.

- *VIA/ELCAP*, the data can be downloaded [here](http://www.via.cornell.edu/lungdb.html). The gold-standard is located at `Materials/via_elcap.zip` in this repository.
- *EXACT09*, the data can be downloaded [here](http://image.diku.dk/exact/). The gold-standard is located at `Materials/exact09.zip` in this repository.
- *LOLA11*, the data can be downloaded [here](https://lola11.grand-challenge.org/). To download the images, one must first register in the competition. The gold-standard is located at `Materials/lola11.zip` in this repository.
- *LIDC IDRI*, the data can be downloaded [here](https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI). The gold-standard is located at `Materials/lidc_idri_part1.zip` and `Materials/lidc_idri_part2.zip` in this repository. The data has been separated into 2 parts because its size exceeded 100MB.

## Implementation
