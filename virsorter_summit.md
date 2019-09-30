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
