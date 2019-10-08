##
**list 1**
OWC-16-2018 metaG, 19Spet2019
```
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D1_reads_and_megahit_full_assembly/Aug_M1_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D2_reads_and_megahit_full_assembly/Aug_M1_C1_D2_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D3_reads_and_megahit_full_assembly/Aug_M1_C1_D3_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D4_reads_and_megahit_full_assembly/Aug_M1_C1_D4_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D5_reads_and_megahit_full_assembly/Aug_M1_C1_D5_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M2_C1_D1_reads_and_megahit_full_assembly/Aug_M2_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M2_C1_D5_reads_and_megahit_full_assembly/Aug_M2_C1_D5_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D1_reads_and_megahit_full_assembly/Aug_N3_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D5_reads_and_megahit_full_assembly/Aug_N3_C1_D5_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D1_reads_and_megahit_full_assembly/Aug_OW2_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D5_reads_and_megahit_full_assembly/Aug_OW2_C1_D5_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D1_reads_and_megahit_full_assembly/Aug_T1_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D5_reads_and_megahit_full_assembly/Aug_T1_C1_D5_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D1_reads_and_megahit_full_assembly/May_M1_C1_D1_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D3_reads_and_megahit_full_assembly/May_M1_C1_D3_megahit_assembly
/home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D6_reads_and_megahit_full_assembly/May_M1_C1_D6_megahit_assembly

```

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit

screen -S virsorter_OWC2018_16contigs
source /opt/Miniconda2/miniconda2/bin/activate   virsorter

for line in $(cat OWC2018_16contigs_path.txt)
do
cd $line
fa=$(ls *MC.fa)
echo $fa
wrapper_phage_contigs_sorter_iPlant.pl --fna $fa --db 2 --ncpu 6 --data-dir /opt/virsorter-data
done


```

## finished on zenith for metaG16,7-OCt-2019
```
conda /opt/Miniconda2/miniconda2/bin/deactivate

```
**remember to clean the renamed contigs file


## collect all virsorter output
```
cd /home/projects/Wetlands/OWC_viral_from_metaG
/home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith

cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit

for line in $(cat OWC2018_16contigs_path.txt)
do
cd $line
fa=$(ls *MC.fa)
#mkdir /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/"${fa%.*}"_virsorter-out
cp -a ./virsorter-out/. /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/"${fa%.*}"_virsorter-out/
#cp virsorter-out /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/"${fa%.*}"_virsorter-out
done

du -sh -- *

#del the file within each assembly
#mv renamed fa to virsorter collections

cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit

for line in $(cat OWC2018_16contigs_path.txt)
do
cd $line
fa=$(ls *MC.fa)
echo "${fa}"
mv ${fa} /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/
rm -r virsorter-out
done

```

## two biggest one 
```
screen -S virsorter_co_megahit_Deep
source /opt/Miniconda2/miniconda2/bin/activate   virsorter

#OwcDeepSubCoMC.fa
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep
wrapper_phage_contigs_sorter_iPlant.pl --fna OwcDeepSubCoMC.fa --db 2 --ncpu 12 --data-dir /opt/virsorter-data

#waiting
#OwcSurfaceSubCoMC.fa
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface

#wrapper_phage_contigs_sorter_iPlant.pl --fna OwcSurfaceSubCoMC.fa --db 2 --ncpu 12 --data-dir /opt/virsorter-data

```
