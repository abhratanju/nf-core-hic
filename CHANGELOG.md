# nf-core/hic: Changelog

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## v1.3.0dev -

### `Added`

* New parameter `--valid_pairs` to start the pipeline after the valid pairs detection
* New parameter `--bams` to start the pipeline after the mapping steps
* New TADs calling process (`--res_tads` and `--skip_tads`)
* New compartments calling process (`--res_compartments` and `--skip_compartments`)
* New distance decay process (`--res_dist_decay` and `--skip_dist_decay`)
* New `--digestion` parameter to automatically set enzymes options
* New `--keep_multi` and `keep_dup` options. Default: false

### `Fixed`

* `min_mapq` is ignored if `--keep_multi` is used

### Deprecated

* `--rm_dup` and `rm_multi` are replaced by `--keep_dup` and `--keep_multi`

## v1.2.0dev - 2020-05-12

### `Added`

* Bump v1.2.0dev
* Merge template nf-core 1.9
* Move some options to camel_case
* Update conda environment file
* Update python scripts for python3

### `Fixed`

* Fix a bug in rm_dup in file sorting

### `Deprecated`

* --skipMaps, --skipIce, --skipCool, --skipMultiQC are deprecated and replaced by --skip_maps, --skip_ice, --skip_cool, --skip_multiqc
* --saveReference, --saveAlignedIntermediates, --saveInteractionBAM are replaced by --save_reference, --save_aligned_intermediates, --save_interaction_bam

## v1.1.1 - 2020-04-02

### `Fixed`

* Fix bug in tag. Remove '['

## v1.1.0 - 2019-10-15

### `Added`

* Update hicpro2higlass with `-p` parameter
* Support 'N' base motif in restriction/ligation sites
* Support multiple restriction enzymes/ligattion sites (comma separated) ([#31](https://github.com/nf-core/hic/issues/31))
* Add --saveInteractionBAM option
* Add DOI ([#29](https://github.com/nf-core/hic/issues/29))
* Update manual ([#28](https://github.com/nf-core/hic/issues/28))

### `Fixed`

* Fix bug for reads extension _1/_2 ([#30](https://github.com/nf-core/hic/issues/30))

## v1.0 - [2019-05-06]

Initial release of nf-core/hic, created with the [nf-core](http://nf-co.re/) template.

### `Added`

First version of nf-core Hi-C pipeline which is a Nextflow implementation of
the [HiC-Pro pipeline](https://github.com/nservant/HiC-Pro/).
Note that all HiC-Pro functionalities are not yet all implemented.
The current version supports most protocols including Hi-C, in situ Hi-C,
DNase Hi-C, Micro-C, capture-C or HiChip data.

In summary, this version allows :

* Automatic detection and generation of annotation files based on igenomes
if not provided.
* Two-steps alignment of raw sequencing reads
* Reads filtering and detection of valid interaction products
* Generation of raw contact matrices for a set of resolutions
* Normalization of the contact maps using the ICE algorithm
* Generation of cooler file for visualization on [higlass](https://higlass.io/)
* Quality report based on HiC-Pro MultiQC module
