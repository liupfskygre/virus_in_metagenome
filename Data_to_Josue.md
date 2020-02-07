##virus contigs and vOTU from OWC_wetland_projects

## part I metafile
```
#Contigs/Scaffold used for virsorter 
Assemblies_for_Virsorter_summary.xlsx

#39 contigs/scaffold files
```


## part II virsorter output related , 10K
```
## virsorter version (1.0.5 on summit and zenith)
wrapper_phage_contigs_sorter_iPlant.pl


## 10K virus contigs
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K

OWC_virsorter_10K_all.fa . # all putative conitigs with virsorter cat-1, 2, 4, 5 from 39 contigs file



#annotation files might be needed for DRAMv
#location of VIRSORTER_AFFI_CONTIGs in Metric_files
#1, cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_zenith 
# sample list --> metaG.list  (16)
for file in $(cat metaG.list)
do
cp "${file}"_virsorter-out/Metric_files/VIRSorter_affi-contigs.tab /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/VIRSorter_affi_contigs_tab_OWC39/"${file}"_VIRSorter_affi-contigs.tab
done


#2, cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/virsorter_from_summit/
sample list --> #metaG_running_on_summit.list #12 samples
 


#3, /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep/virsorter-out/Metric_files/VIRSorter_affi-contigs.tab
#-->1 sample 


#4,  /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface/virsorter_co_megahit_Surface_10K/Metric_files/VIRSorter_affi-contigs.tab 
#-->1 sample 


#5, cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/Virus_metaG2014_15
# -->9 samples


#collect all affi file for dramV, VIRSorter_affi-contigs.tab
mkdir /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/VIRSorter_affi_contigs_tab_OWC39


```


## part III, vOTU data
```
Cluster_genomes_5.1.pl

cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K

Cluster_genomes_5.1.pl -f OWC_virsorter_10K_all.fa -c 80 -i 95 -t 6


OWC_virsorter_10K_all_95-80.fna  ## vOTU with cutoff 95-80, # 4436 seqs

```


## part IV, vConTACT2_0.9.8

*this part has been done
```
<<vOTU file: OWC_virsorter_10K_all_95-80.fna; for 
>vConTACT2_0.9.8 (21-Nov-19, newest one on cyverse)

# /Users/pengfeiliu/A_Wrighton_lab/Wetland_project/OWC_metaG_2014_2018/Virus_OWC/OWC_virsorter_10K

```

##note 
```

```
