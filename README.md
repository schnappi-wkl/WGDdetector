# WGDdetector

WGDdetector: a pipeline for whole genome duplication (WGD) detecting with the genome or transcriptome annotations

# Install
## Software requirements
* perl >5.0, including the perl moudule of threads and Bioperl
* python 2.7
* R >= 3.5

* parallel
* mmseqs2 
* blast >= ncbi-blast-2.2.28+
* BlastGraphMetrics (https://github.com/trgibbons/BlastGraphMetrics) 
* mcl 
* mafft

## Pipline install
This pipline is a series perl scripts, you can just replace those scripts' header with the right perl path
```
cd WGDdetector_path
perl setup.pl
```

# Running 

```
wgddetector (v1.00)

Usage: wgddetector --input_cds <cds_file> --input_pep <pep_file> --output_dir <output_dir> --tmp_dir <tmp_dir> --thread_num <thread_num> --cluster_engine <blastp|mmseqs2>

Options:
        --input_cds      input CDS in fasta format
        --input_pep      input protein in fasta format
        --output_dir     the output dir, which containing the main results
        --tmp_dir        the tmp dir
        --thread_num     the thread number when runnig this script
        --cluster_engine "blastp" or "mmseqs2". when setted this as mmseqs2, the protein aligning and clustering will be faster than blast
        --clean          "yes" or "no". If selected yes, the tmp_dir will removed after finish. Default: yes
        --run_cluster    "yes" or "no". If selected yes, the protein blast and mcl clustering will generate. If selected no, the clustering file "output_dir/01.cluster/all-protein-clustering.result" must be existed

  ** The sequence IDs within the CDS and protein files must be same!
```