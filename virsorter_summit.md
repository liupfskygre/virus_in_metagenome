## this is a markdown file for how to run virsorter on summit 

##check here, 

## https://github.com/liupfskygre/OWC_metaG16_ana2019/edit/master/How_to_summit.md

run_virsorter_summit.sh

```
for line in $(cat OWC2018_16contigs_path.txt)
do
cd $line
fa=$(ls *MC.fa)
echo $fa
wrapper_phage_contigs_sorter_iPlant.pl --fna $fa --db 2 --ncpu 6 --data-dir /projects/liupf@colostate.edu/scripts/virsorterDB/virsorter-data
done
```

## log in and folder
```
ssh liupf@colostate.edu@login.rc.colorado.edu

#projects
cd /projects/liupf@colostate.edu

#scratch
cd /scratch/summit/liupf@colostate.edu

$/opt/globusconnectpersonal-2.3.6/globusconnectpersonal -start &

$ /opt/globusconnectpersonal-2.3.6/globusconnectpersonal -stop

```

#data on zenith, WOC_2018_metaG16 were running on zenith
```
/home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_TF_1/NoSub_Soil_TF_1_megahit
/home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_T3_3/NoSub_Soil_T3_3_megahit
/home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface
/home/projects/Wetlands/All_genomes/DDIG_megahit_assemblies
/home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies

```

#transfer contigs to summit
```
cd /scratch/summit/liupf@colostate.edu
mkdir OWC_contigs_for_virsorter

#transfer the ones renamed for virsorter
#14 files being transfered


```

```
conda activate virsorter
#
# To deactivate an active environment, use
#
#     $ conda deactivate
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 4.3G Sep 30 12:21 M3C4D3v1MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 4.9G Sep 30 12:20 M3C4D3v2MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 5.6G Sep 30 12:19 M3C4D4MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  21G Sep 30 12:22 M3C5D1DdigMC.fa

#485M Sep 30 12:09 NoSubSoilT33MC.fa
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh NoSubSoilT33MC

-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 297M Sep 30 12:08 NoSubSoilTF1MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  20G Sep 30 12:25 O3C3D1DdigMC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  19G Sep 30 12:27 O3C3D3DdigMC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 5.3G Sep 30 12:19 O3C3D3MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  18G Sep 30 12:30 O3C3D4DdigMC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu 5.3G Sep 30 12:20 O3C3D4MC.fa
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  38G Sep 30 12:12 OwcDeepSubCoMC.fa
# 990M Sep 30 12:09 OwcEnrich2015IDBA.fa
sbatch run_virsorter_summit_24h.sh OwcEnrich2015IDBA 
-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  55G Sep 30 12:16 OwcSurfaceSubCoMC.fa

```
#test
```
cd /scratch/summit/liupf@colostate.edu/OWC_contigs_for_virsorter
conda activate virsorter
wrapper_phage_contigs_sorter_iPlant.pl --fna NoSubSoilT33MC.fa --db 2 --ncpu 1 --data-dir /scratch/summit/liupf@colostate.edu/scripts/virsorterDB/virsorter-data 


```



```
/projects/liupf@colostate.edu/


```
