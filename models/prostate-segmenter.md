---
layout: model
type: "model"
model-name:  "Prostate-Segmenter"
description: "Whole-gland prostate segmentation in pelvic Axial T2-W MRI scans."
modality: "MRI"
organ: "Prostate"
task: "Segmentation"
train_no: "60"
test_no: "30"
license_type: "Slicer License"
license_url: "https://github.com/Slicer/Slicer/blob/master/License.txt"
performance: "Dice: %85"
input: "Pelvic T2-W MRI"
size: "6.8 GB"
maintainer:     "Alireza Mehrtash"
email:     "mehrtash at bwh.harvard.edu"
header-img: "img/demo-screen-1.png"
---

### Slicer module guide

### Command-line guide

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
