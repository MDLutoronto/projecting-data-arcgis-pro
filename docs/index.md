---
title: "Projecting your data in ArcGIS Pro"
layout: "home"
description: ""
permalink: "/"  #! Remove this if not the homepage
---

# Projecting your data in ArcGIS Pro

In order for many GIS functions to work properly, your datasets need to be stored in a common projected coordinate system. This guide will assist you with the projection process in ArcGIS Pro. (Unsure of what the appropriate projection is for your area of interest? Refer to this [help document](https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection) or ask a staff member for assistance in helping you determine it.)

1. Use the Add Data button to add each of the datasets you wish to convert to the map document.

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_001.png' | relative_url }}' alt='ArcGIS Pro ribbon with Add Data tool found underneath the Maps tab, outlined in red.' title='' width='648%' height='' />
2. You can find out what coordinate system each layer is associated with by right\-clicking on the layer name in the Contents pane, selecting **Properties…** and clicking on the **Source** tab in the Layer Properties window.

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_002_2.png' | relative_url }}' alt='Contents pane showing Properties selected in blue.' title='' width='45%' height='' />

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_003.png' | relative_url }}' alt='Source tab of Layer Properties, with Spatial Reference menu expanded. ' title='' width='100%' height='' />
3. To project your layers, open the ArcToolbox window by clicking on the red toolbox found in the Analysis tab. Expand Data Management Tools, then Projections and Transformations. To project vector datasets double\-click on Project. For raster datasets, expand Raster then double\-click on Project Raster.

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_004_0.png' | relative_url }}' alt='ArcGIS Pro ribbon showing the Tools button found underneath the Analysis tab, outlined in red.' title='' width='648%' height='' /><img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_005_0.png' | relative_url }}' alt='Geoprocessing pane showing the location of the Project tool found by navigating to the Projections and Transformation tab in Data Management Tools.' title='' width='35%' height='' />
4. In the **Input Dataset or Feature Class box** (labeled Input Raster in the Project Raster tool), use the dropdown menu to select the dataset you are looking to project. (If it has not yet been loaded into the map document, click on the folder icon to browse to the appropriate folder and select it.)  
The software should auto\-detect the coordinate system of this dataset and will list it as **Input Coordinate System**.

    In the **Output Dataset or Feature Class/Output Raster** box, browse to the location where you would like to save the projected dataset and specify the filename. It is a good idea to indicate that these are the projected versions of other datasets, e.g. by adding “\_projected” to the end of each filename.

    Click the icon next to the **Output Coordinate System** box to select the projection that you would like to assign to the dataset. (Tip: if another one of your layers already has the correct projection selected, you can use the Import tool to find the right projection faster.) If the transformation involves a change in datum, you will be prompted to select a geographic transformation in the following box – a list of applicable transformations will be found in the **Geographic Transformation** dropdown menu. Click OK to project your dataset. When all your datasets are projected, you should begin a new map document (or manually change the coordinate system of the data frame to match your datasets) before conducting any spatial analysis.

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_006_0.png' | relative_url }}' alt='Project tool window with GCS_North_American_1983 as the selected Input Coordinate System.' title='' width='75%' height='' />
5. *For advanced users*: Are you looking to project a number of vector datasets at once? You can use the Batch Project function (located within ArcToolbox \> Data Management Tools \> Projections and Transformations \> Batch Project) to project several at the same time. However, you may need to run the function multiple times, one for each group of input datasets that share a particular datum.

    e.g. all datasets going from GCS\_North\_American\_1983 to NAD\_1983\_UTM\_Zone\_17N will need to be done as one batch, all datasets going from GCS\_WGS\_1984 to NAD\_1983\_UTM\_Zone\_17N as another batch…

    Before beginning the Batch Project process, you will need to note the appropriate geographic transformation to use for each set of datum shifts. You can do that by opening up the Project tool again, selecting an input dataset and the output coordinate system, and taking note of the recommended geographic transformations that appear in the dropdown menu. You’ll need to write down the exact name of the geographic transformation applicable to each group of datasets that you will be projecting – note that if you are projecting into a coordinate system that uses the same datum as the input datasets, no geographic transformation is required (such as the GCS\_North\_American\_1983 to NAD\_1983\_UTM\_Zone\_17N example mentioned above).

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_007_0.png' | relative_url }}' alt='Project tool window with GCS_WGS_1984 as the selected Output Coordinate System, highlighted in red.' title='' width='75%' height='' />

    The Batch Project tool works much in the same way as the Project tool outlined in this tutorial, except the Geographic Transformation needs to be typed into the **Transformation box**, instead of selected from a dropdown list of potential options.

    <img src='{{ '/assets/images/Projecting_your_data_in_ArcGIS_Pro_008_1.png' | relative_url }}' alt='Batch Project window with WGS_1984_(ITRF00)_To_NAD_1983 as the Transformation that has been typed in.' title='' width='75%' height='' />

Technique: [Projecting](/technique/projecting) \| Tools: [ArcGIS Pro](/taxonomy/term/70) \| Data Format: [Raster](/data-format/raster), [Vector](/data-format/vector)**Date Created:** 2024\-01\-08**Updated:** 2024\-01\-15
