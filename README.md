# ARCs

## ARC directory structure

`/isa.investigation.xlsx`
: main investigation file (in XLSX format), contains top-level information about the investigation and links to assays

`/isa.studies.xlsx`
: (optional) posibillity to group assays into studies within one investigation, contains mostly sample characteristics 

`/LICENSE` 
: license file for the arc

`/arc.cwl`
: (optional) executes all runs



### Assay

All measurment (self generated) datasets are considert as assays (immutable input data)

`/assays/<assay>`
: folder for an essay, name is arbitrary

`/assays/<assay>/dataset`
: assay dataset

`/assays/<assay>/protocols`
: assay protocol as text (e.g SOP)

`/assays/<assay>/isa.tab`
: per-assay ISA file, contains only info about this assay (in XLSX format)


### workflows (aka. codespace, code, code capsules, codecaps)

All programmatic components of an ARC should go here, in the form of code and environment.

`/workflows/<yourWorkflowsName>/`
: folder for code and its environment (workflow specifications), contains all files needed to specify a workflow. Also packages and other includes needed should go here.

`/workflows/<yourWorkflowsName>/Dockerfile`
: top-level Dockerfile [optional] in which all code/workflow should execute

`//workflows/<yourWorkflowsName>//[codefiles;...]`
: code files/scripts for computation

### Externals

The place for external data (mapping files, gene info, etc.)

`/externals/[e.g. mapman-ontology-301120.txt;...]`
: external reference / knowledge files, hard included

`/externals/isa.tab`
: description of external reference / knowledge files, XLSX format

### Runs (aka. computations)

Runs are all artefacts that result by some computation from the assays.

`/runs/<yourRunResultName>`
: folder for results of your run aka. workflow execution

`/runs/<runResultName>/[files;...]`
: run result files (plots, tables, etc. )

`/runs/<runResultName>.cwl`
: executes a script or workflow and produces run results accordingly.