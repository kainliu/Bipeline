# Bipeline

Bipeline: A Web-Based Visualization Tool for Biclustering of Multivariate Time Series, ECML-PKDD 2016

http://link.springer.com/chapter/10.1007/978-3-319-46131-1_3

Author: Ricardo Cachucho(r.cachucho@liacs.leidenuniv.nl), Kaihua Liu(k.liu.5@umail.leidenuniv.nl)

**Bipeline is online now**: http://fr.liacs.nl:7000/


Bipeline aims to provide toolkits to explore datasets in a visualized way, especially for time-series datasets. It includes dataset *uploading*, *plotting*, *pre-processing*, *segmenting* and *biclustering*, which offer handy access of different methods and parameters applied to your data.

![modules](https://raw.githubusercontent.com/kainliu/Bipeline/master/screenshot/modules.png)


## Abstract

Large amounts of multivariate time series data are being generated every day. Understanding this data and finding patterns in it is a contemporary task. To find prominent patterns present in multivariate time series, one can use biclustering, that is looking for patterns both in subsets of variables that show coherent behavior and in a number of time periods. For this, an experimental tool is needed.


Here, we present Bipeline, a web-based visualization tool that provides both experts and non-experts with a pipeline for experimenting with multivariate time series biclustering. With Bipeline, it is straightforward to save experiments and try different biclustering algorithms, enabling users to intuitively go from pre-processing to visual analysis of biclusters.

## Stages

### Importing

Users could upload dataset and view details with a data table and summary info, e.g. Min. Max. and Mean.

### Plotting

It's often of high importance to have a visual inspection of the raw time series first before digging into details. Plotting panel includes *plotting*, *multi-plotting* and *correlation* tab. 

An interactive plotting R package dygraphs *dygraphs* is implemented instead of traditional static image plotting, which allows part of time series to be selected for zooming in. Zoom in/out functionality is one of the most desired characteristics of visual inspection tools for large time series dataset. 

In *multi-plotting* tab, each of selected variables is plotted in an individual dygraphs plot, and zoom in/out of any of them will be synchronized across all plots. Correlation tab uses simple linear regression to plot a fit line for selected *X* and *Y* variables.


![plotting](https://raw.githubusercontent.com/kainliu/Bipeline/master/screenshot/plotting.png)


### Pre-processing

![pre-processing](https://raw.githubusercontent.com/kainliu/Bipeline/master/screenshot/pre-processing.png)

Raw data often requires error handling such as: 
* Exclude variables; 
* Normalization;
* Conditions, to remove or replace conditional data lines; 
* Outlier Removal, as shown above: selecting data points that are furthest away from the average, as candidates to be removed. 

Users could execute iterative process of `*plotting* <==> *pre-processing*` until the data is ready, then export pre-processed data to local disks by clicking *Save* button, or continue moving to *segementation* and *biclustering*.

### Segmentation ###

![segmentation](https://raw.githubusercontent.com/kainliu/Bipeline/master/screenshot/segmentation.png)


By default, all variables share the same setting of parameters in segmentation. By selecting the names of variables, control panel will update dynamically created tabs for users to set individual arguments, which offers great flexibility. Window Size, overlap, threshold and variate type could be easily tuned with clicks and drags. 

The minimum segment size is customizable, and the tool will merge short segments in the union of segmentation boundaries by comparing similarities between siblings.

Segmentation results could be saved \& loaded, which is useful when users have finished segmentation step and they can directly jump to biclustering step by loading previous saved segmentation files. These results will be used in the following biclustering step by default, however, user could disable that in baseline biclustering methods by unchecking corresponding option.


### Biclustering ###

![biclustering](https://raw.githubusercontent.com/kainliu/Bipeline/master/screenshot/biclustering.png)


