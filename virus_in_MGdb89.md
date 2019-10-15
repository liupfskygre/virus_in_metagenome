## this is Markdown file

## using virsorter to scan virus in Methangoens db89

#should I do virosorter on deRep genomes or all genomes??
```
cd /home/projects/Wetlands/2018_sampling/Methanog_targeted_coassembly/Methanogens_final_dRep_clean_db

screen -S virsorter_MGdb89
source /opt/Miniconda2/miniconda2/bin/activate   virsorter

wrapper_phage_contigs_sorter_iPlant.pl --fna OWC_methanogens_DB89_cat.fna --db 2 --ncpu 6 --data-dir /opt/virsorter-data

```
