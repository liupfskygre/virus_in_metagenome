## running vConTACT on vOTUs

#ref
```
https://bitbucket.org/MAVERICLab/vcontact2/src/master/
https://ivirus.readthedocs.io/en/latest/Protocols.html

#following the toturial from Josue
```

#
```
#wkdir: run vConTACT2 on cyverse

1. input file
protein files generated from vOTU 

# /Users/pengfeiliu/A_Wrighton_lab/Wetland_project/OWC_metaG_2014_2018/Virus_OWC/OWC_virsorter_10K

<<vOTU file: OWC_virsorter_10K_all_95-80.fna; # 4436

prodigal -i OWC_virsorter_10K_all_95-80.fna -a OWC_virsorter_10K_all_vOTU_protein.faa -p meta


2. vConTACT2_0.9.5 or vConTACT2_0.9.8
# https://de.cyverse.org/de/

1> vContact2-Gene2Genome_1.1.0_analysis1: 
#para, Prodigal amino acid proteins

2>vConTACT2_0.9.8 (21-Nov-19, newest one on cyverse)
#Gene-to-Genome mapping file. MUST BE PROVIDED if using raw proteins or BLASTP/Diamond. from last step
# para: defaults

```
