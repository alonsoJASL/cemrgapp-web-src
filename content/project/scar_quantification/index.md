---
title: Scar Quantification
summary: Estimate Fibrosis from a pair of CEMRA and LGE-CMR scans.
tags:
  - mri
  - atria
  - machine learning
date: '2016-01-01'

authors: 
  - 

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: 
  focal_point: Smart

links:
  - icon: file
    icon_pack: fas
    name: PAR
    url: 'https://github.com/CemrgAppDevelopers/resources/blob/main/par/Rigid_MRI.cfg'
url_code: ''
url_pdf: 'https://github.com/CemrgAppDevelopers/resources/blob/main/sop/CemrgApp-AtrialScarProcessing.pdf'
url_slides: ''
url_video: 'https://www.youtube.com/watch?v=JtbA0wBcqd8'

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Atrial fibrillation (AF) is a heart condition that causes an irregular and often abnormally fast heart rate. Fibrosis is a major contributor to sustained AF. Late gadolinium enhancement (LGE) cardiac magnetic resonance imaging (CMR) is currently the only available tool for its non-invasive assessment. This plugin was developed to facilitate, visualise and validate the multiple analysis steps required for the assessment of fibrosis and quantification of scarred tissue.

The plugin contains data processing toolkits, which perform resampling, automatic segmentation, rigid registration and transformation of images, bespoke smoothing of segmentations, LGE image interrogation, and assessment of fibrosis. All these steps are automated in an end-to-end workflow.

The workflow contains a multi-label convolutional neural network (CNN), designed to accurately delineate atrial structures including the blood pool, pulmonary veins and mitral valve. The output from the network removes the user dependent steps and allows for reproducible quantification of fibrosis from scans.

The network was trained and tested on a dataset of 207 manually labelled scans and a 
 Dice score was achieved for atrial blood pool segmentation. The network was also checked against the “2018 Atrial Segmentation Challenge” dataset to evaluate its potential limitations on analysing different scans from a different centre. The network without any retraining on the challenge dataset achieved a Dice score of 
. Retraining the network on this dataset achieved a Dice score of 0.89. Testing the network against the “2013 Left Atrial Segmentation Challenge” yielded a Dice score of 
. Although our results show the robustness of the network when tested against these multi-centre datasets, there will be cases, where the network fails. In such cases, the user has the option to use the MITK manual segmentation tools and carry on with the rest of fibrosis quantification process.

The network was trained on 2D slices extracted from the 3D scans using a dedicated GPU machine. At the run time, the plugin initially slices the scan into 2D images, performs the prediction using the pretrained network, and finally puts the results back together. This method has been used in previous medical segmentation methods and helps with keeping the method computationally tractable without losing significant performance.

Additionally, the “Advanced Calculations” toolkit of this plugin can quantify extra features in the scar tissue, with an emphasis on the tissue’s status before and after pulmonary vein isolation (PVI). PVI is a common ablation procedure that prevents abnormal electrical signals from activating the atrium by electrically isolating the pulmonary veins. A successful ablation produces a lesion encircling the veins that stops the activation.