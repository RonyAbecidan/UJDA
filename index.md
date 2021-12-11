#### Rony Abecidan, Vincent Itier, Jeremie Boulanger, Patrick Bas
 [![](https://img.shields.io/badge/Article-2E86C1?style=for-the-badge)](https://hal.archives-ouvertes.fr/hal-03374780/)  [![](https://img.shields.io/badge/GitHub-000000?style=for-the-badge&logo=github&logoColor=white)](https://gitlab.cristal.univ-lille.fr/pbas/unsupervisedjpegadaptation) 

*Domain adaptation is a major issue for doing practical forensics. Since examined images are likely to come from a different development pipeline compared to the ones used for training our models, that may disturb them by a lot, degrading their performances. In this paper, we present a method enabling to make a forgery detector more robust to distributions different but related to its training one, inspired by Long et. al (2015) . The strategy exhibited in this paper foster a detector to find a feature invariant space where source and target distributions are close. Our study deals more precisely with discrepancies observed due to JPEG compressions and our experiments reveal that the proposed adaptation scheme can reasonably reduce the mismatch, even with a rather small target set with no labels when the source domain is properly selected. On top of that, when a small portion of labelled target images is available this method reduces the gap with mix training while being unsupervised.*


### Don't hesitate to click on the figures below to see them better

[![](https://svgshare.com/i/cX6.svg)](https://svgshare.com/i/cX6.svg)

## Architecture used

[![](https://svgshare.com/i/cWR.svg)](https://svgshare.com/i/cWR.svg)


## Domain Adaptation in action

- **Source** : Half of images from the Splicing category of DEFACTO 
- **Target** : Other half of the images from the Splicing category of DEFACTO, compressed to JPEG with a quality factor of 5%

To have a quick idea of the adaptation impact on the training phase, we selected a batch of size 512 from the target and, we represented the evolution of the final embeddings distributions from this batch during the training according to the setups **SrcOnly** and **Update($`\sigma=8`$)**
described in the paper. The training relative to the SrcOnly setup is on the left meanwhile the one relative to **Update($`\sigma=8`$)** is on the right.

[![](https://s10.gifyu.com/images/Adaptationf80f69ab9e1dfcaa.gif)](https://s10.gifyu.com/images/Adaptationf80f69ab9e1dfcaa.gif)

- As you can observe, in the **SrcOnly** setup, the forgery detector is more and more prone to false alarms, certainly because compressing images to QF5 results in creating artifacts in the high frequencies that can be misinterpreted by the model. However, it has no real difficulty to identify correctly the forged images.

- In parallel, in the **Update** setup, the forgery detector is more informed and make less false alarms during the training.

## Main references

```BibTeX
@inproceedings{mandelli2020training,
  title={Training {CNNs} in Presence of {JPEG} Compression: Multimedia Forensics vs Computer Vision},
  author={Mandelli, Sara and Bonettini, Nicol{\`o} and Bestagini, Paolo and Tubaro, Stefano},
  booktitle={2020 IEEE International Workshop on Information Forensics and Security (WIFS)},
  pages={1--6},
  year={2020},
  organization={IEEE}
}

@inproceedings{bayar2016,
  title={A deep learning approach to universal image manipulation detection using a new convolutional layer},
  author={Bayar, Belhassen and Stamm, Matthew C},
  booktitle={Proceedings of the 4th ACM workshop on information hiding and multimedia security (IH\&MMSec)},
  pages={5--10},
  year={2016}
}

@inproceedings{long2015learning,
  title={Learning transferable features with deep adaptation networks},
  author={Long, M. and Cao, Y. and Wang, J. and Jordan, M.},
  booktitle={International Conference on Machine Learning},
  pages={97--105},
  year={2015},
  organization={PMLR}
}


@inproceedings{DEFACTODataset, 
	author = {Ga{\"e}l Mahfoudi and Badr Tajini and Florent Retraint and Fr{\'e}d{\'e}ric Morain-Nicolier and Jean Luc Dugelay and Marc Pic},
	title={DEFACTO: Image and Face Manipulation Dataset},
	booktitle={27th European Signal Processing Conference (EUSIPCO 2019)},
	year={2019}
}
```

---
### If you wish to refer to our paper,  please use the following BibTeX entry
```BibTeX
@inproceedings{abecidan:hal-03374780,
  TITLE = {Unsupervised JPEG Domain Adaptation for Practical Digital Image Forensics},
  AUTHOR = {Abecidan, Rony and Itier, Vincent and Boulanger, J{\'e}r{\'e}mie and Bas, Patrick},
  URL = {https://hal.archives-ouvertes.fr/hal-03374780},
  BOOKTITLE = {{WIFS 2021 : IEEE International Workshop on Information Forensics and Security}},
  ADDRESS = {Montpellier, France},
  PUBLISHER = {{IEEE}},
  YEAR = {2021},
  MONTH = Dec,
  PDF = {https://hal.archives-ouvertes.fr/hal-03374780/file/2021_wifs.pdf},
  HAL_ID = {hal-03374780}
}
```
