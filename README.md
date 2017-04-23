# nctc

Pipeline facilitating access to complete bacterial reference assemblies from public repositories:
* maintain complete reference genomes (PacBio) from [NCTC3000](http://www.sanger.ac.uk/resources/downloads/bacteria/nctc/)
* type assemblies (local and database) with [mlst](https://github.com/tseemann/mlst) and [Abricate](https://github.com/tseemann/abricate)
* collect analysis summaries for local sequences or species from NCTC3000

## Data Usage

Please refer to data usage guidelines from [NCTC3000](http://www.sanger.ac.uk/resources/downloads/bacteria/nctc/):

>This sequencing centre plans on publishing the completed and annotated sequences in a peer-reviewed journal as soon as possible. Permission of the principal investigator should be obtained before publishing analyses of the sequence/open reading frames/genes on a chromosome or genome scale. See our data sharing policy.

Assemblies can be updated by users with task 'update':

>**Please note**: these are pre-submission assemblies that should not be treated as final versions. Assemblies contain both chromosomal and plasmid contigs.

## Setup

Dependencies:

* [Anaconda](https://www.continuum.io/DOWNLOADS) for Python 3

Clone this repository recursively to include latest version of Abricate:

```bash
git clone --recursive https://github.com/esteinig/nctc
```

Create environment with dependencies:

```
conda env create -f nctc/env/nctc.yaml
```

Activate environment before executing tasks:

```
source activate nctc
```

Print help message for global options and task options:

```
nctc --help

nctc make --help
nctc type --help
nctc collect --help
```

## Quick Start

```
source activate nctc

nctc --project ./ref_db --species "Escherichia coli" make --chromosomes
nctc --project ./ref_db --species "Escherichia coli" type --v vfdb --r resfinder
nctc --project ./ref_db --species "Escherichia coli" collect --cnv --csv --output ./summary
```

## Tasks

`make`

`type`

`collect`

`update`
