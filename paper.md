---
title: ': browser-based coastal shoreline detection and mapping'
tags:
  - Python
  - shoreline
  - satellite-derived shoreline
  - coastal dynamics
  - google earth engine
  - Doodleverse
  - semantic segmentation
authors:
  - name: Sharon Fitzpatrick
    orcid: 0000-0001-6513-9132
    affiliation: 1
  - name: Daniel Buscombe
    orcid: 0000-0001-6217-5584
    affiliation: 1    
  - name: Jonathan Warrick
    orcid: 0000-0002-0205-3814
    affiliation: 2  
  - name: Kilian Vos
    orcid: 0000-0002-9518-1582
    affiliation: 3      
affiliations:
 - name: Contracted to U.S. Geological Survey Pacific Coastal and Marine Science Center
   index: 1
 - name: U.S. Geological Survey Pacific Coastal and Marine Science Center
   index: 2
 - name: NSW Australia
   index: 3   
date: 21 December 2023
bibliography: paper.bib
---

# Summary

``CoastSeg`` is an interactive python package that allows users to download satellite imagery, identify shorelines in satellite imagery, and generate a time series of shoreline change. ``CoastSeg`` includes multiple jupyter notebooks that allow users to download satellite data, automatically extract shorelines from their satellite data, apply tide correction to their shorelines all within one experience. ``CoastSeg`` extends the functionality of other similar tools such as CoastSat by enabling users to see the data they want to download, see their shorelines on the map, and more all within one tool. Normally users would need to switch between a variety of tools to download the satellite data, extract shorelines, apply tidal correction, and more, but ``CoastSeg`` allows users to do all this in a single location all with a completely reproducible workflow.


# Statement of Need
In today's technological landscape, we have access to extensive collections of satellite data spanning decades. However, it's only in recent years that advancements in algorithms, machine learning, and deep learning have enabled the automation of processing this satellite imagery to accurately identify and understand its features. While a variety of independent tools are available, both free and subscription-based, to assist in data processing, using these tools often require researchers to navigate amongst various platforms, develop custom code, and  it means switching amongst various tools, writing custom code to process the data,and engage in substantial manual efforts to extract meaningful features from the imagery.

``CoastSeg`` is a free, open-source Python package that makes it easy to download satellite imagery, extract shorelines from hundreds to thousands of images all with one package. ``CoastSeg`` is an interactive package that provides all the necessary tools to make it easy to extract shorelines from satellite imagery. It allows users to see their extracted shorelines on the map, makes it easy to download data from Google Earth Engine, and makes tide correction much easier than existing tools. ``CoastSeg`` is built using some functionality from another Python software Coastsat [site] and with Leafmap [site]. The advantages of using ``CoastSeg`` over CoastSat are that with ``CoastSeg`` you can easily see what data you want to download on the mapping interface [reference figure], downloaded data & extracted shorelines can be shared with other users through a session system and a tide correction workflow is included making ``CoastSeg`` a all in one tool for extracting shorelines.

# Implementation of CoastSat workflow

``CoastSeg`` provides functionality to load geojson features onto the map to make the process of extracting shorelines more interactive. Users can see which regions they will download data within, which reference shoreline will be used to find the shorelines in the imagery, and the transects that will be used to measure shoreline change.  Other tools exist to perform similar functionality but lack the user interface that helps guide the user through the process. ``CoastSeg`` provides default reference shorelines and transects that can be used to extract shorelines, so users do not need to provide their own data or draw their own reference shoreline.

``CoastSeg`` is built with a object architecture. Objects on the map like ROIs, shorelines and transects each have their own class which stores the data for that feature type as well as methods related to styling the feature on the map, downloading default features, and various post processing functions.

 ``CoastSeg`` employs a session-based system that enables users to track what data they’ve downloaded before and run experiments with different settings to extract optimal shorelines. This session system is what makes ``CoastSeg`` fully reproducible because all the settings, inputs, and outputs are stored within each session as well as a reference to what downloaded data was used to generated the extracted shorelines in the session. These sessions can be shared with other users allowing other users to reproduce experiments or share data that was downloaded by another user. This feature encourages collaboration and experimentation across users.

# Implementation of Segmentation Zoo workflow

The combination of speed,
design, and support for Astropy functionality in ``Gala`` will enable exciting
scientific explorations of forthcoming data releases from the *Gaia* mission
[@gaia] by students and experts alike. The source code for ``Gala`` has been
archived to Zenodo with the linked DOI: [@zenodo]

# Acknowledgements

We acknowledge contributions from Brigitta Sipocz, Syrtis Major, and Semyeong
Oh, and support from Kathryn Johnston during the genesis of this project.

# References
## Other Related Software
- coastsat
- coastsat_package
- zoo
- leafmap
- geemap