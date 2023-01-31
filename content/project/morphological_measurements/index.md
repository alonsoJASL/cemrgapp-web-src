---
title: Morphological Measurements
summary: Analyse remodelling of heart’s chambers from cardiac scans by assessing volume, surface area, wall thickness, and associated vessels morphological characteristics.
tags:
  - ct
  - ventricles
  - atria
date: ''

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: 
  focal_point: Smart

links:
  - icon: file
    icon_pack: fas
    name: PAR
    url: 'https://github.com/CemrgAppDevelopers/resources/blob/main/par/Nonrigid_CT.cfg'
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''
# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---

Remodelling of heart chambers is a common feature of many cardiovascular conditions and is a sensitive marker of adverse cardiovascular outcomes. The aim of this plugin is to analyse remodelling of heart’s chambers from cardiac scans by assessing volume, surface area, wall thickness, and associated vessels morphological characteristics.

The plugin provides a semi-automatic method of segmenting the blood pool and the cardiac wall using an iterative growing algorithm, which detects pixels within a signal intensity range corresponding to muscular tissue of the heart. A high-resolution tetrahedral mesh is then constructed from the wall segmentation using CGAL. The mesh is subsequently processed to tag the endocardial (inner) and epicardial (outer) surface layers.

To calculate tissue thickness, the Laplace equation is solved with Dirichlet boundary conditions assigned at the endocardial and epicardial surfaces to generate a series of nested iso-potential surfaces. Wall thickness is evaluated as the length of the path between the endocardium and epicardium when moving orthogonally between adjacent iso-potential surfaces. Tissue thickness measurements are associated with each mesh node.

In order to truncate vessels and calculate their morphological characteristics, a Voronoi diagram is utilised by the plugin. This diagram is extracted from a surface mesh made from the blood pool segmentation. Each of the vessels is initially identified by the user placing landmarks on the distal ends of the mesh in a 3D VTK renderer, which was specifically designed for dealing with user interactions more effectively than the default MITK 3D visualisation window. Centrelines are then automatically drawn from these points to the centre of the body using the VMTK library. As the centrelines enter the body, the maximum area of the surrounding structure increases significantly. This inflection is used to identify the opening of the chamber. Then, a fully automatic clipper computes the geometric properties of the vessels’ inner walls and truncates the blood pool precisely at the opening point.
