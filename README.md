# Establishing Glacier Inventory

![Satellite Image](/photos/glaciers.jpg)

This repository contains geospatial resources essential for the development of glacier inventory of any designated years using open-source approach. This case study outlines overall geospatial practices in glacier mapping and final output generation using free and open-source multispectral satellites, terrain information, and softwares/platforms such as Google Earth Engine, QGIS and python.

All shared materials in this repository can be used, modified, shared with proper citations.

Supplementary materials [here](/supplementary/).
Access GEE scripts [here](/GEE_scripts/).

**Example Case Study**: Afghanistan

**Used Satellite Imagery**: Landsat series, MODIS Snow Dataset, SRTM DEM

**Softwares**: QGIS, Google Earth Engine, Python

_All materials prepared by Swun Wunna Htet (2026)._
___

Disclaimer: The applied geospatial functions can vary depending on specific conditions, and country. Refer to it with caution.

```mermaid
---
title: Development Workflow for a single inventory year 
---

flowchart TB
    A["`**Satellite Imagery**`"]

    subgraph P["`**Elimination of Seasonal Snow**`"]
        direction LR
        B[/Preprocessing/]
        C[/Ablation Peak \nPeriod Determination/]
        B-->C
    end

    subgraph Z["`**Satellite Image Composite**`"]
        direction LR
        D[/Data Filtering, \nQuality Mask, clipping to \nAOI/]
        E[/Composite Imagery\n Generation/]
        D-->E
    end

    subgraph Y["`**Glacier Mapping**`"]
        direction LR
        F[/Ground Truth Collection \n& EDA/]
        G[/Supervised \nClassification/]
        H[/Accuracy \nAssessment/]
        I[/Post-Processing/]

        F-->G
        G-->H
        H--Good-->I
        H--No Good-->G
    end

    subgraph X["`**Glacier Attributes**`"]
        direction LR
        J[/Attributes based on\n GLIMS format/]
    end

    K[("`**Glacier Inventory (.gpkg)**`")]


    A==>P
    P==>Z
    Z==>Y
    Y==>X
    X==>K
```

___

