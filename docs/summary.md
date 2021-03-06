# Summary Presentation

## Introduction 
As part of the 2019 NLM Reproducibility workshop,five of us attempted to reproduce the work in the paper:
A functional genomics predictive network model identifies regulators of inflammatory bowel disease



## Approaches to reproduce paper


## Obstacles

### Data


The referenced epigenetic region data is not clearly specified. Instead of providing specifiers about _what_ data was used, the paper merely references GEO data is available at NCBI: http:// www.ncbi.nlm.nih.gov/geo/roadmap/epigenomics/

### Synapse

Other data is supposed to be available via Synapse platform (Sage Bionetworks https://www.synapse.org/IBDNetworks), however, the provided link/identifier does not work.  (the work was found after creating an account and using their search feature. The data was instead at: https://www.synapse.org/#!Synapse:syn10792659


Furthermore, some of the data appears to be corrupted and others appears to be missing entirely. For example, a large 16Gb data file would not download (the system cites that the MD5 signature does not match the data on the system). 

There are empty directories in their work.  

There was significant problems trying to download the data from Synapse platform. In order to download data from Synapse, you must use their software. There is a link for "Download Options",  - and there were two options: 
(1) Add to download list
(2) Programmatic options

I could not easily figure out how to use "add to download list". It appears that there isn't an easy way to download the entire project all at once. When I attempted to use the "download list", I got the error/warning:
```
If a folder contains no files, no files will be added to the download list. Additionally, sub-folders cannot be added directly; please navigate into the directory that contains the files you’d like to download to add them.
```
(This appears to mean that the "add to download list" only downloads 1 level deep? which is not good for trying to download the entire project all at once - meaning a piecemeal attempt is required.)

The second approach is to use "programmatic options". However, there were significant issues with this approach.
The command line option was to use `synapse` command - but it was not inherently obvious how to get it. There appeared to be a couple of pieces of software when searching with google.

We attempted to use the python programmatic approach. Documentation
signifcant problems with their code (for example the required `synapseutils.py` could not be found anywhere for installation).


```
    Python
    R
    Command Line

								
 import synapseclient
 import synapseutils
 
 syn = synapseclient.Synapse()
 syn.login('synapse_username','password')
 files = synapseutils.syncFromSynapse(syn, 'syn10792659')
``` 

							
