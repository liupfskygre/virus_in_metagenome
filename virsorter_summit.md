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
#conda activate vs_105
use source activate vs_105 inside slurm
#
# To deactivate an active environment, use
#
#     $ conda deactivate


cd /scratch/summit/liupf@colostate.edu/OWC_contigs_for_virsorter

#485M Sep 30 12:09 NoSubSoilT33MC.fa
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh NoSubSoilT33MC ##
# no results??? dir of data is not right

$# 990M Sep 30 12:09 OwcEnrich2015IDBA.fa
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh OwcEnrich2015IDBA  ##

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh M3C4D3v1MC

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh M3C4D3v2MC

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh M3C4D4MC

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh NoSubSoilTF1MC

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh O3C3D3MC

sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_24h.sh O3C3D4MC.fa

---->>>
## following use high mem, 48 cores, long
#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  21G Sep 30 12:22 
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d.sh M3C5D1DdigMC ##waiting
# sbatch: deprecation: long qos is redundant for smem; changing to normal

##change to use shas
cp /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d.sh /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh
nano /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh

#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  20G Sep 30 12:25 
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh O3C3D1DdigMC ## running
Submitted batch job 3231694


#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  19G Sep 30 12:27 
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh O3C3D3DdigMC

#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  18G Sep 30 12:30 
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh O3C3D4DdigMC

#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  38G Sep 30 12:12 
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh OwcDeepSubCoMC

#-rwxr-x---. 1 liupf@colostate.edu liupfgrp@colostate.edu  55G Sep 30 12:16  
sbatch /projects/liupf@colostate.edu/workspace/run_virsorter_summit_7d_shas.sh OwcSurfaceSubCoMC

```
#test
```
cd /scratch/summit/liupf@colostate.edu/OWC_contigs_for_virsorter
conda activate virsorter # not working in slurm scripts, 
wrapper_phage_contigs_sorter_iPlant.pl --fna NoSubSoilT33MC.fa --db 2 --ncpu 1 --data-dir /scratch/summit/liupf@colostate.edu/scripts/virsorterDB/virsorter-data 
# worked

```
## notes
```
#1, use 
source activate vs_105 #inside slurm

#2, install by miniconda directly instead of github help page, 

```


#
```
(base) [liupf@colostate.edu@shas0136 OWC_contigs_for_virsorter]$ squeue |grep liupf
           3231704      shas virsorte liupf@co PD       0:00      1 (Priority)
           3231705      shas virsorte liupf@co PD       0:00      1 (Priority)
           3231706      shas virsorte liupf@co PD       0:00      1 (Priority)
           3231707      shas virsorte liupf@co PD       0:00      1 (Priority)
           3231682      smem virsorte liupf@co PD       0:00      1 (Priority)
           3231700      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231699      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231698      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231697      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231701      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231702      shas mapping_ liupf@co PD       0:00      1 (Priority)
           3231694      shas virsorte liupf@co  R       2:04      1 shas0513
           3231664      shas mapping_ liupf@co  R       9:34      1 shas0109
           3231650      shas mapping_ liupf@co  R      21:39      1 shas0664

scancel
```
