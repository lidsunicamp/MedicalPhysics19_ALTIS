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

The implementation of ALTIS is located at the folder `bin/` of this repository. It is the 64-bit binary version for Ubuntu 16.04. In order to run the software, just run the following commands.

```
$cd <path_to_ALTIS_binary>
$iftALTIS -i <input_ct_image> -o <output_label_mask> --improve-segmentation 25
```

The file formats accepted by the software are: .nii, .nii.gz, .hdr, .scn. The `--improve-segmentation` flag is optional and is used when some parts of the lungs are left outside the segmentation. It will perform an extra delineation step to try to solve this problem. To see the all available flags of this software, just add the flag `-h` or `--help`.

Remember, in order for ALTIS to run correctly, the input image must be isotropic, i.e. the voxel size is the same in every dimension. Additionally, the method assumes that the patient orientation in the CT scan is from inferior to superior along the axial slices (z-axis), from right to left along the sagittal slices (x-axis), and from anterior to posterior along the coronal slices (y-axis). Therefore, in a coronal slice, the lungs and trachea appear in the upright position, being the right lung on the left side of the slice.
