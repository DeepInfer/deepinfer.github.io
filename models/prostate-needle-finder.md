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
input: "Pelvic T2-W MRI"
size: "6.8 GB"
maintainer:     "Alireza Mehrtash"
email:     "mehrtash at bwh.harvard.edu"
header-img: "img/demo-screen-1.png"
---
### Prostate Needle Finder Demo
<div class="row">
<div class="col-md-6">
<div class="embed-responsive embed-responsive-16by9">
<iframe src="https://www.youtube.com/embed/cKKjTxR-DxQ?rel=0&amp;showinfo=0" frameborder="1" allow="autoplay;" allowfullscreen></iframe>
</div>
</div>
</div>

### Slicer module guide


### Command-line interface guide
#### Download Docker Image
```
docker pull deepinfer/deepinfer-prostate
```
#### Run Example 
```
docker run -t -v ~/data/prostate_test/:/data deepinfer/prostate\
                   --ModelName prostate-segmenter\
                   --Domain BWH_WITHOUT_ERC\
                   --InputVolume prostate.nrrd \
                   --OutputLabel output_prostate_label.nrrd \
                   --ProcessingType Accurate\
                   --Inference Ensemble\
                   --verbose
```
#### Inputs
```
[Mandatory]
ModelName: ('prostate-needle-finder')
InputVolume: (an existing filename locating the T2-Weighted Pelvic MRI containing MRI)

[Optional]
```
<!-- ### Related blog posts -->

### Reuse and Citations
The {{page.model-name}} model is licensed under [{{page.license_type}}]({{page.license_url}}).<br>
For attribution in academic contexts, please cite the following work(s):

```
Article under review.
```
BibTeX citation

```
@inproceedings{,
  title={},
  author={},
  booktitle={},
  volume={},
  year={},
  organization={}
}
```