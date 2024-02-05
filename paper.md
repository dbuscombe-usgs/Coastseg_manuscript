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


- add a section that explains that coasteg is extendable
- users can create their own workflows by adding a new notebook and calling the coastseg api


# Statement of Need
In today's technological landscape, we have access to extensive collections of satellite data spanning decades. However, it's only in recent years that advancements in algorithms, machine learning, and deep learning have enabled the automation of processing this satellite imagery to accurately identify and understand its features. While a variety of independent tools are available, both free and subscription-based, to assist in data processing, using these tools often require researchers to navigate amongst various platforms, develop custom code, and  it means switching amongst various tools, writing custom code to process the data,and engage in substantial manual efforts to extract meaningful features from the imagery.

``CoastSeg`` is a free, open-source Python package designed to streamline the process of downloading satellite imagery and extracting shorelines from a large volume of images, all within a single integrated platform. ``CoastSeg`` simplifies the extraction of shorelines from satellite imagery by providing comprehensive tools for the entire process. Users can view their extracted shorelines directly on the map, easily download data from Google Earth Engine, and perform tide corrections more efficiently than with existing tools.


  ``CoastSeg`` differentiates itself from the similar software CoastSat [site] by providing an interactive mapping interface, a session system that makes experimenting to discover the setting that optimal extract shorelines from satellite imagey.  ``CoastSeg`` incorperates  functionality from other Python packages Coastsat [site] and Leafmap [site].

  - Rephrase this to say coastseg is built with coastsat and leafmap to make it extendable and customizable
 - Organize how coastseg improves on coastsat
 - mention stable downloads, provides default shorelines and transects, detailed logs and sharable sessions

 The advantages of using ``CoastSeg`` over CoastSat are that with ``CoastSeg`` you can easily see what data you want to download on the mapping interface [reference figure], downloaded data & extracted shorelines can be shared with other users through a session system and a tide correction workflow is included making ``CoastSeg`` a all in one tool for extracting shorelines. This makes ``CoastSeg`` a more advanced and user-friendly alternative to CoastSat, offering a seamless, end-to-end experience for users in this field.

# Implementation of CoastSat workflow

## Key Improvements to Highlight

``CoastSeg`` offers a user-friendly and interactive approach to shoreline extraction from satellite imagery. Its interface allows users to visually identify and select specific regions of interest (ROI) to download multispectral data at. Once the data has been aquired users can load their reference shorelines and transects onto the map to gain a spatial understanding of where in their imagery CoastSeg will attempt to the load the reference shoreline from. While there are other tools with similar capabilities, they often fall short in providing an intuitive user interface that simplifies and guides the process. A standout feature of "CoastSeg" is its provision of default reference shorelines and transects. This eliminates the need for users to supply their own data or manually draw reference shorelines, making it significantly more accessible and user-friendly, especially for those new to the field or without extensive technical backgrounds.

## Architecture & Design

``CoastSeg`` is built with a object-oriented architecture, where elements on the map such as  Regions of Interest (ROIs), shorelines, and transects are represented as distinct classes. Each class not only stores data specific to that feature type but also encompasses methods for styling the feature on the map, downloading default features, and executing various post-processing functions.

- Here we could introduce that CoastSeg can be extended by adding additonal notebooks?

## Reproducibility

- this doesn't really flow nicely
- introduce what sessions achieve
- explain what a session is
- what it is used to do
- how it can be shared
- how this feature is useful in a research context


 ``CoastSeg`` employs a session-based system that 
 enables users to iteratively experiment with different combinations of settings in order to extract optimal shorelines. Each time the user makes adjustments to the settings used to extract shorelines from the imagery a new session folder is saved with the updated settings.  This session system is what makes ``CoastSeg`` fully reproducible because all the settings, inputs, and outputs are stored within each session as well as a reference to what downloaded data was used to generate the extracted shorelines in the session. 
 
 Moreover, the session system in "CoastSeg" fosters a collaborative environment. Users can share their sessions with others, enabling peers to replicate experiments, build upon previous work, or access data downloaded by someone else.This not only simplifies the process for new users but also encourages collective experimentation and data sharing. Such a feature is particularly beneficial in a research context, where reproducibility and collaboration are key to advancing knowledge and understanding in the field of shoreline extraction.



# Implementation of Segmentation Zoo workflow

- modify this section to be how coastseg can be extended with the new workflows
- built on top of leafmap to make it easy to add new functionality
- foreshadow the zoo workflow

# Acknowledgements

- todo

# References
## Other Related Software
- coastsat
- coastsat_package
- zoo
- leafmap
- geemap