## About

dcm_qa_nih is a simple DICOM to NIfTI validator script and dataset. This repository is similar to [dcm_qa](https://github.com/neurolabusc/dcm_qa), but includes data from both GE as well as Siemens MRI scanners.

## License

This software and images are open source and were acquired by National Institutes of Health. The the code is covered by the [2-clause BSD license](https://opensource.org/licenses/BSD-2-Clause).

## Versions

18-September-2018
 - Initial public release

## Running

Assuming that the executable dcm2niix is in your path, you should be able to simply run the script `batch.sh` from the terminal.

If you have problems you can edit the first few lines of the `batch.sh` script so that `basedir` reports the explicit location of the `dcm_qa` folder (by default this is assumed to be the folder containing the script) on your computer and `exenam` reports the explicit location of dcm2niix (by default it is assumed to be in your path). Also, make sure the script is executable (`chmod +x batch.sh`). Then run the script.

## Updating dcm_qa_nih

This software reports when there are any changes in behavior of the software. However, some of these changes might be improvements. For example, software which supports future BIDS tags will report differences relative to the prior solutions reported in dcm_qa_nih. Once the solutions have been verified as correct, one needs to update both dcm_qa_nih and the software that invokes dcm_qa_nih. For example, with dcm2niix we can update it to use the latest version of dcm_qa with this script:

```
cd dcm2niix
git submodule update --remote
git commit -am 'Update dcm_qa_nih submodule.'
git push
```

## Useful Links

 - The dataset acquisition is described [here](https://docs.google.com/document/d/1ii--eAuvvP-RIuJNvJjkz-1h0LgyfsTATkPwkuKH7uc/edit#heading=h.n43cfjeo2cq2).
 - This dataset was acquired to support regression tests for software run on GE scanners as described [here](https://github.com/rordenlab/dcm2niix/issues/163).
 - Some descriptions of terminology relevant to the GE metadata can be found [here](https://docs.google.com/document/d/1-ytyPg32i_9vmMyILR3hZYP8gVtDOwv0DQSWnznyFjM/edit).
 - [Details on GE information is provided in this header](https://github.com/ScottHaileRobertson/GE-MRI-Tools/blob/master/GePackage/%2BGE/%2BPfile/%2BHeader/%2BRDB15/rdbm.h).
 - [Stanford provides useful tips](https://cni.stanford.edu/wiki/GE_Processing).
 - [UCSD provides nice tips](https://cfmriweb.ucsd.edu/Howto/3T/operatingtips.html).
 - [NITRC hosts GE validation datasets from the NIH, Nicolaus Copernicus University, and the University of Iowa](https://www.nitrc.org/plugins/mwiki/index.php/dcm2nii:MainPage#Slice_timing_correction).
 - [nikadon](https://github.com/nikadon/cc-dcm2bids-wrapper/tree/master/dicom-qa-examples) provides a similar GE validation dataset demonstrating slice timing, phase encoding polarity, and diffusion features.
