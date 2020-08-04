---
layout: model
type: "model"
model-name:  "Prostate-Needle-Finder"
description: "Biopsy needle trajectory and tip detection in intraoperative MRIs."
modality: "MRI"
organ: "Prostate"
task: "Localization, Segmentation"
train_no: "50 patients (410 MRIs)"
test_no: "21 patients (173 MRIs)"
license_type: "Slicer License"
license_url: "https://github.com/Slicer/Slicer/blob/master/License.txt"
performance: "Mean needle tip localization error: 2.8 mm"
input: "1) Pelvic T2-W MRI, 2)Prostate gland segmentation (Approximate)"
output: "1)Biopsy Needle Segmentation, 2)Fiducial list containing needle tip"
size: "6.8 GB"
maintainer:     "Alireza Mehrtash"
email:     "mehrtash at bwh.harvard.edu"
header-img: "img/demo-screen-1.png"
---


### Scientific Publication
Details for {{page.model-name}} model are provided in the following scientific publication:
```
Mehrtash, Alireza, et al. "Automatic needle segmentation and localization in MRI with 3-D 
convolutional neural networks: application to MRI-targeted prostate biopsy." 
IEEE transactions on medical imaging 38.4 (2018): 1026-1036.
```
BibTeX citation

```
@article{mehrtash2018automatic,
  title={Automatic needle segmentation and localization in MRI with 3-D convolutional neural networks: application to MRI-targeted prostate biopsy},
  author={Mehrtash, Alireza and Ghafoorian, Mohsen and Pernelle, Guillaume and Ziaei, Alireza and Heslinga, Friso G and Tuncali, Kemal and Fedorov, Andriy and Kikinis, Ron and Tempany, Clare M and Wells, William M and others},
  journal={IEEE transactions on medical imaging},
  volume={38},
  number={4},
  pages={1026--1036},
  year={2018},
  publisher={IEEE}
}
```

### License
{{page.model-name}} model is licensed under [{{page.license_type}}]({{page.license_url}}).<br>

<!--For attribution in academic contexts, please cite the following work(s):-->

### Demo
<div class="row">
<div class="col-md-6">
<div class="embed-responsive embed-responsive-16by9">
<iframe src="https://www.youtube.com/embed/cKKjTxR-DxQ?rel=0&amp;showinfo=0" frameborder="1" allow="autoplay;" allowfullscreen></iframe>
</div>
</div>
</div>


### Command-line interface guide
#### Download Docker Image
```
docker pull deepinfer/prostate
```
#### Example
```
docker run -t -v ~/data/needle_test/:/data deepinfer/prostate\
                   --ModelName prostate-needle-finder\
                   --InputVolume /data/confirmation_volume.nrrd\
                   --InputProstateMask /data/prostate_label.nrrd\
                   --OutputLabel /data/needle_label.nrrd \
                   --OutputFiducialList /data/Tip.fcsv\
                   --InferenceType Single\
                   --verbose
```
#### Inputs
```
[Mandatory]
ModelName: ('prostate-needle-finder')
InputVolume: (an existing filename locating the T2-Weighted Pelvic MRI containing Needle)
InputProstateMask: (an existing filename locating the rough prostate gland location)
OutputLabel: (output path of the needle label)
OutputFiducialList: (output path of the fiducial list in fcsv format (slicer fiducial list format) where the needle
tip will be saved)
Inference: (Single, Ensemble)
    Single: the prediction would be the output of a single model. Ensemble: the prediction will be the 
    calculated by ensembling of 5 models from 5-fold cross validation and majority voting.

[Optional]
verbose : 
verbose mode for printing additional details about the procedure.
```
<!-- ### Related blog posts -->

