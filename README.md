# ARCs

## ARC directory structure

`/isa.tab`
: main investigation file (in XLSX format), contains top-level information about the investigation and links to assays

`/arc.cwl`
: executes all results cwls


### Assay

`/assays/<assay>`
: folder for an essay, name is arbitrary

`/assays/<assay>/dataset`
: assay dataset

`/assays/<assay>/protocols`
: assay protocol as text (e.g SOP)

`/assays/<assay>/isa.tab`
: per-assay ISA file, contains only info about this assay (in XLSX format)


### Workflows

All programmatic components of an ARC should go here, in the form of workflows.

`/workflows/`
: folder for workflow specifications

/workflows/Dockerfile
: top-level Dockerfile [optional] in which all workflows should execute (individual workflows can specify their own Dockerfiles)

`/workflows/<workflow>/`
: per-workflow folder, contains all files needed to specify a workflow

`/workflows/<workflow>/code`
: code for workflow

`/workflows/<workflow>/code/something.r`  
`/workflows/<workflow>/code/generic.cwl`


#### Sample ARC workflow in F#

`/workflow/libfubar/code/bla.fs`  
`/workflow/libfubar/code/blu.fs`  
`/workflow/libfubar/code/blo.fs`  
`/workflow/libfubar/generic.cwl`  
`/workflow/libfubar/fubar.packages`

Interactive notebook workflow:

`/results/notebook/test.ipynb`

use case:  
```git submodule add /workflows/<foo> git://...```


### Results

Results are all artefacts that result by some computation from the assays.

`/results/<name>.cwl`
    - do XY plot on assay1 using XYworkflow -> XY.png
    - do PCA on assay1 using PCAworkflow -> PCA.txt
`/results/<name>/plot1.png`  
`/results/<name>/table.csv`  
`/results/<name>/fubar.txt`


### External

`/external/mapman-ontology-301120.txt`
: external reference / knowledge files, hard included

`/external/isa.tab`
: description of external reference / knowledge files, XLSX format
