---
layout: model
type: "model"
model-name:  "Prostate-Segmenter"
description: "Whole-gland prostate segmentation in pelvic Axial T2-W MRI scans"
modality: "MRI"
organ: "Prostate"
task: "Segmentation"
train_no: "60"
test_no: "30"
license_type: "Slicer License"
license_url: "https://github.com/Slicer/Slicer/blob/master/License.txt"
performance: "Dice: %85"
input: "Pelvic T2-W MRI"
output: "Prostate gland binary segmentation"
size: "6.8 GB"
maintainer:     "Alireza Mehrtash"
email:     "mehrtash at bwh.harvard.edu"
header-img: "img/demo-screen-1.png"
---

### Demo
<div class="row">
<div class="col-md-6">
<div class="embed-responsive embed-responsive-16by9">
<iframe src="https://www.youtube.com/embed/BgqUzAwMfvQ?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>
</div>
</div>


### Command-line guide
#### Download Docker Image
```
docker pull deepinfer/prostate
```
#### Example
```
docker run -t -v ~/data/prostate_test/:/data deepinfer/prostate\
                   --ModelName prostate-segmenter\
                   --Domain BWH_WITHOUT_ERC\
                   --InputVolume /data/prostate.nrrd \
                   --OutputLabel /data/output_prostate_label.nrrd \
                   --ProcessingType Accurate\
                   --Inference Ensemble\
                   --verbose
```
#### Inputs
```
[Mandatory]
ModelName: (prostate-segmenter)
Domain: (BWH_WITH_ERC, BWH_WITHOUT_ERC, PROMISE12)
    Select the domain of trained models: 3 different domains are available:
    - BWH_WITH_ERC is a domain trained on pre-operative T2-Weighted images of Brigham and Women's Hosptial
    with endorctal coil on 3T MRI machine.
    - BWH_WITHOUT_ERC is a domain trained on pre-operative T2-Weighted images of Brigham and Women's Hosptial
    with endorctal coil on 3T MRI machine.
    - PROMISE12 are models that are trained on PROMISE12 challenge training dataset (multi-center multi-vendor dataset) 
    (https://promise12.grand-challenge.org/)
InputVolume: (an existing filename locating the T2-Weighted Pelvic MRI containing MRI)
OutputLabel: (output path of the prostate gland label)
ProcessingType: (Fast, Accurate)
    Accurate models use higher resolution inputs (0.27-0.625 mm in-plane resolutions) while fast models use
    1 mm in-plane resolutions.
Inference: (Single, Ensemble)
    Single: the prediction would be the output of a single model. Ensemble: the prediction will be the 
    calculated by ensembling of 5 models from 5-fold cross validation and majority voting.
[Optional]
verbose : 
    verbose mode for printing additional details about the procedure.
```

<!--### Related blog posts

* <a href="/jekyll/2017/06/10/prostate-volume-measurement/">Prostate volumetric measurements in MRI with DeepInfer and 3D Slicer</a-->

### Reuse and Citations
The {{page.model-name}} model is licensed under [{{page.license_type}}]({{page.license_url}}).<br>
For attribution in academic contexts, please cite the following work(s):

```
Mehrtash A. et al. "DeepInfer: open-source deep learning deployment toolkit for image-guided therapy." SPIE 2017.
```
BibTeX citation

```
@inproceedings{mehrtash2017deepinfer,
  title={DeepInfer: Open-Source Deep Learning Deployment Toolkit for Image-Guided Therapy},
  author={Mehrtash, Alireza and Pesteie, Mehran and Hetherington, Jorden and Behringer, Peter A and Kapur, Tina and Wells III, William M and Rohling, Robert and Fedorov, Andriy and Abolmaesumi, Purang},
  booktitle={Proceedings of SPIE--the International Society for Optical Engineering},
  volume={10135},
  year={2017},
  organization={NIH Public Access}
}
```
