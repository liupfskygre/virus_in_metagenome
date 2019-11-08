##
#DRAMv on 10k virsorter contigs vOTU
```
source /opt/Miniconda2/miniconda2/bin/activate DRAM

DRAM.py annotate -i scaffold_error.fa -o annotated_DRAM_error --threads 24

DRAM.py summarize_genomes -i annotated_DRAM_error/annotations.tsv -o genome_summaries_error --trna_path annotated_DRAM_error/trnas.tsv
```

```
#
DRAM.py annotate_viral -i INPUT_FASTA -v VIRSORTER_AFFI_CONTIGs -o [OUTPUT_DIR]


```

## preparation of VIRSORTER_AFFI_CONTIGs?
#for examples
#/home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_summit/AugOW2C1D5MC/Metric_files
```
#zenith, 16 samples
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_zenith
touch VIRSorter_affi-contigs_zenith.tab

for file in $(cat metaG.list)
do
cat ${file}_virsorter-out/Metric_files/VIRSorter_affi-contigs.tab >> VIRSorter_affi-contigs_zenith.tab
done 

#summit, 12 samples, other samples running on zenith were used
#/home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_summit/
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_summit/
touch VIRSorter_affi-contigs_summit.tab
for file in $(cat metaG.list)
do
cat ${file}/Metric_files/VIRSorter_affi-contigs.tab >> VIRSorter_affi-contigs_summit.tab
done 

# 
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/
cat virsorter_from_summit/VIRSorter_affi-contigs_summit.tab  virsorter_from_zenith/VIRSorter_affi-contigs_zenith.tab > VIRSorter_affi-contigs_all30.tab

#
#
cat /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep/virsorter-out/Metric_files/VIRSorter_affi-contigs.tab >> VIRSorter_affi-contigs_all30.tab

cat /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface/virsorter_co_megahit_Surface_10K/Metric_files/VIRSorter_affi-contigs.tab >> VIRSorter_affi-contigs_all30.tab
```

#
```
mv VIRSorter_affi-contigs_all30.tab ./OWC_virsorter_10K
grep -e '>' OWC_virsorter_10K_all_95-80.fna > OWC_virsorter_10K_all_95-80_header.txt . #4313

sed -e  's/_-cat.*$//g' OWC_virsorter_10K_all_95-80_header.txt >OWC_virsorter_10K_all_95-80_header_fixed.txt 
sed -i -e 's/_-circular.*$//g' OWC_virsorter_10K_all_95-80_header_fixed.txt 
sed -i -e 's/_gene.*$//g' OWC_virsorter_10K_all_95-80_header_fixed.txt 

sed -i -e 's/_$//g' OWC_virsorter_10K_all_95-80_header_fixed.txt 

sed -i -e 's/-cat.*$//g' OWC_virsorter_10K_all_95-80_header_fixed.txt 
sed -i -e 's/-circular.*$//g' OWC_virsorter_10K_all_95-80_header_fixed.txt 
cat OWC_virsorter_10K_all_95-80_header_fixed.txt|sort|uniq > OWC_virsorter_10K_all_95-80_header_fixed_uniq.txt
#4306

grep -f OWC_virsorter_10K_all_95-80_header_fixed_uniq.txt VIRSorter_affi-contigs_all30.tab >VIRSorter_affi-contigs_all30_vOTU.tab
#3xxxx?? 
# 
```



#
```
DRAM.py annotate_viral -i OWC_virsorter_10K_all_95-80.fna -v VIRSorter_affi-contigs_all30_vOTU.tab -o OWC_virsorter_10K_all_95_80_dram
#DRAM.py annotate_viral: error: the following arguments are required: -v/--virsorter_affi_contigs
```
