##

#1 tranfer data from zenith to MAC
```
Add the sample name of to header 
#sampleidentifierwithoutunderscores_scaffold_0
sed -e 's/>\(k.*\)/>\1_/1'
``
# example for megahit contigs
```
head Aug_M1_C1_D1_megahit.contigs.fa > example.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' example.fa>example1.fa
sed -i -e 's/>\(k.*\)/>example1_\1/1' example1.fa
```

## OWC_2018_metaG16
**1, Aug_M1_C1_D1_megahit_assembly	1	Aug_M1_C1_D1 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D1_reads_and_megahit_full_assembly/Aug_M1_C1_D1_megahit_assembly
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D1_megahit.contigs.fa >AugM1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D1MC_\1/1' AugM1C1D1MC.fa  #MC stands for Megahit_Contigs
```

**2, Aug_M1_C1_D2_megahit_assembly	1	Aug_M1_C1_D2 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D2_reads_and_megahit_full_assembly/Aug_M1_C1_D2_megahit_assembly
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D2_megahit.contigs.fa >AugM1C1D2MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D2MC_\1/1' AugM1C1D2MC.fa  #MC stands for Megahit_Contigs
```
