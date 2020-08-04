---
layout: model
type: "model"
model-name:  "WMH-Segmenter-K2"
description: "Team K2's solution for WMH segmentation grand challenge (http://wmh.isi.uu.nl/) at MICCAI 2017."
modality: "MRI"
organ: "Brain"
task: "Lesion Segmentation"
train_no: "60"
test_no: "110"
license_type: "Slicer License"
license_url: "https://github.com/Slicer/Slicer/blob/master/License.txt"
performance: "Dice: %77, H95: 9.79 mm"
input: "Brain Axial T1-W MRI and FLAIR"
output: "White matter hyperintensities binary segmentation maps"
size: "6.4 GB"
maintainer: "Alireza Mehrtash"
email:     "mehrtash at bwh.harvard.edu"
header-img: "img/demo-screen-1.png"
---
### Demo
<div class="row">
<div class="col-md-6">
<div class="embed-responsive embed-responsive-16by9">
<iframe src="https://www.youtube.com/embed/nOlTVD0Gigk?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>
</div>
</div>

### Command-line guide
```
docker pull deepinfer/wmh-segmenter-k2
```
#### Example
```
docker run -t -v ~/data/wmh_test/:/data deepinfer/whm-segmenter-k2\
                   --ModelName wmh_segmenter\
                   --InputT1Volume /data/T1.nrrd\
                   --InputFLAIRVolume /data/flair.nrrd\
                   --OutputLabel /data/wmh_label.nrrd \
                   --verbose
```
#### Inputs
```
[Mandatory]
ModelName: ('wmh_segmenter')
InputT1Volume: (an existing filename locating the T1-Weighted MRI of the brain)
InputFLAIRVolume: (an existing filename locating the FLAIR MRI of the brain)
OutputLabel: (output path of the white matter hyperintensity (WMH) label)

[Optional]
verbose : 
verbose mode for printing additional details about the procedure.
```

<!--### Related blog posts-->

### Reuse and Citations
The {{page.model-name}} model is licensed under [{{page.license_type}}]({{page.license_url}}).<br>
For attribution in academic contexts, please cite the following work(s):

```
Kuijf, Hugo J., et al. "Standardized assessment of automatic segmentation of white matter 
hyperintensities and results of the WMH segmentation challenge." 
IEEE transactions on medical imaging 38.11 (2019): 2556-2568.
```
BibTeX citation

```
@article{kuijf2019standardized,
  title={Standardized assessment of automatic segmentation of white matter hyperintensities and results of the WMH segmentation challenge},
  author={Kuijf, Hugo J and Biesbroek, J Matthijs and De Bresser, Jeroen and Heinen, Rutger and Andermatt, Simon and Bento, Mariana and Berseth, Matt and Belyaev, Mikhail and Cardoso, M Jorge and Casamitjana, Adria and others},
  journal={IEEE transactions on medical imaging},
  volume={38},
  number={11},
  pages={2556--2568},
  year={2019},
  publisher={IEEE}
}
```
