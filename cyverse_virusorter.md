##

#1 tranfer data from zenith to MAC
```
Add the sample name of to header 
#sampleidentifierwithoutunderscores_scaffold_0
sed -e 's/>\(k.*\)/>\1_/1'
```
# example for megahit contigs
```
head Aug_M1_C1_D1_megahit.contigs.fa > example.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' example.fa>example1.fa
sed -i -e 's/>\(k.*\)/>example1_\1/1' example1.fa
```

## OWC_2018_metaG16
**1, Aug_M1_C1_D1_megahit_assembly	1	Aug_M1_C1_D1 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D1_reads_and_megahit_full_assembly/Aug_M1_C1_D1_megahit_assembly
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D1_megahit.contigs.fa >AugM1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D1MC_\1/1' AugM1C1D1MC.fa  #MC stands for Megahit_Contigs
```

**2, Aug_M1_C1_D2_megahit_assembly	1	Aug_M1_C1_D2 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D2_reads_and_megahit_full_assembly/Aug_M1_C1_D2_megahit_assembly
head Aug_M1_C1_D2_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D2_megahit.contigs.fa >AugM1C1D2MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D2MC_\1/1' AugM1C1D2MC.fa  #MC stands for Megahit_Contigs
```

**3, Aug_M1_C1_D3_megahit_assembly	1	Aug_M1_C1_D3 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D3_reads_and_megahit_full_assembly/Aug_M1_C1_D3_megahit_assembly
head Aug_M1_C1_D3_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D3_megahit.contigs.fa >AugM1C1D3MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D3MC_\1/1' AugM1C1D3MC.fa  #MC stands for Megahit_Contigs
```

**4, Aug_M1_C1_D4_megahit_assembly	1	Aug_M1_C1_D4 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D4_reads_and_megahit_full_assembly/Aug_M1_C1_D4_megahit_assembly
head Aug_M1_C1_D4_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D4_megahit.contigs.fa >AugM1C1D4MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D4MC_\1/1' AugM1C1D4MC.fa  #MC stands for Megahit_Contigs
```

**5, Aug_M1_C1_D5_megahit_assembly	1	Aug_M1_C1_D5 Megahit full assembly**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M1_C1_D5_reads_and_megahit_full_assembly/Aug_M1_C1_D5_megahit_assembly
head Aug_M1_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M1_C1_D5_megahit.contigs.fa >AugM1C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugM1C1D5MC_\1/1' AugM1C1D5MC.fa  #MC stands for Megahit_Contigs
```

**6, Aug_M2_C1_D1_megahit_assembly	1	Aug_M2_C1_D1 Megahit full assembly**	
```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M2_C1_D1_reads_and_megahit_full_assembly/Aug_M2_C1_D1_megahit_assembly

head Aug_M2_C1_D1_megahit.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M2_C1_D1_megahit.contigs.fa >AugM2C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugM2C1D1MC_\1/1' AugM2C1D1MC.fa  #MC stands for Megahit_Contigs
```

**7, Aug_M2_C1_D5_megahit_assembly	1	Aug_M2_C1_D5 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_M2_C1_D5_reads_and_megahit_full_assembly/Aug_M2_C1_D5_megahit_assembly
head Aug_M2_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_M2_C1_D5_megahit.contigs.fa >AugM2C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugM2C1D5MC_\1/1' AugM2C1D5MC.fa  #MC stands for Megahit_Contigs
```

**8, Aug_N3_C1_D1_megahit_assembly	1	Aug_N3_C1_D1 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D1_reads_and_megahit_full_assembly/Aug_N3_C1_D1_megahit_assembly
head Aug_N3_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_N3_C1_D1_megahit.contigs.fa >AugN3C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugN3C1D1MC_\1/1' AugN3C1D1MC.fa  #MC stands for Megahit_Contigs
```

**9, Aug_N3_C1_D5_megahit_assembly	1	Aug_N3_C1_D5 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D5_reads_and_megahit_full_assembly/Aug_N3_C1_D5_megahit_assembly
head Aug_N3_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_N3_C1_D5_megahit.contigs.fa >AugN3C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugN3C1D5MC_\1/1' AugN3C1D5MC.fa  #MC stands for Megahit_Contigs
```

**10, Aug_OW2_C1_D1_megahit_assembly	1	Aug_OW2_C1_D1 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D1_reads_and_megahit_full_assembly/Aug_OW2_C1_D1_megahit_assembly
head Aug_OW2_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_OW2_C1_D1_megahit.contigs.fa >AugOW2C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugOW2C1D1MC_\1/1’ AugOW2C1D1MC.fa  #MC stands for Megahit_Contigs
```

**11, Aug_OW2_C1_D5_megahit_assembly	1	Aug_OW2_C1_D5 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D5_reads_and_megahit_full_assembly/Aug_OW2_C1_D5_megahit_assembly
head Aug_OW2_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_OW2_C1_D5_megahit.contigs.fa >AugOW2C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugOW2C1D5MC_\1/1’ AugOW2C1D5MC.fa  #MC stands for Megahit_Contigs
```

**12, Aug_T1_C1_D1_megahit_assembly	1	Aug_T1_C1_D1 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D1_reads_and_megahit_full_assembly/Aug_T1_C1_D1_megahit_assembly
head Aug_T1_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_T1_C1_D1_megahit.contigs.fa >AugT1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugT1C1D1MC_\1/1’ AugT1C1D1MC.fa  #MC stands for Megahit_Contigs
```

**13, Aug_T1_C1_D5_megahit_assembly	1	Aug_T1_C1_D5 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D5_reads_and_megahit_full_assembly/Aug_T1_C1_D5_megahit_assembly
head Aug_T1_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_T1_C1_D5_megahit.contigs.fa >AugT1C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugT1C1D5MC_\1/1’ AugT1C1D5MC.fa  #MC stands for Megahit_Contigs
```

**14, May_M1_C1_D1_megahit_assembly	1	May_M1_C1_D1 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D1_reads_and_megahit_full_assembly/May_M1_C1_D1_megahit_assembly
head May_M1_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D1_megahit.contigs.fa >MayM1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D1MC_\1/1’ MayM1C1D1MC.fa  #MC stands for Megahit_Contigs
```

**15, May_M1_C1_D3_megahit_assembly	1	May_M1_C1_D3 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D3_reads_and_megahit_full_assembly/May_M1_C1_D3_megahit_assembly
head May_M1_C1_D3_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D3_megahit.contigs.fa >MayM1C1D3MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D3MC_\1/1’ MayM1C1D3MC.fa  #MC stands for Megahit_Contigs
```

**16, May_M1_C1_D6_megahit_assembly	1	May_M1_C1_D6 Megahit full assembly	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D6_reads_and_megahit_full_assembly/May_M1_C1_D6_megahit_assembly
head May_M1_C1_D6_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D6_megahit.contigs.fa >MayM1C1D6MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D6MC_\1/1’ MayM1C1D6MC.fa  #MC stands for Megahit_Contigs
```

**17, NoSub_Soil_TF_1_megahit.contigs.fa	1	2018, methyl-Enrichment, Kayla	

```
cd /home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_TF_1/NoSub_Soil_TF_1_megahit
head NoSub_Soil_TF_1_megahit.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' NoSub_Soil_TF_1_megahit.contigs.fa >NoSubSoilTF1MC.fa
sed -i -e 's/>\(k.*\)/>NoSubSoilTF1MC_\1/1’ NoSubSoilTF1MC.fa  #MC stands for Megahit_Contigs
```

**18, NoSub_Soil_T3_3_megahit.contigs.f 1	2018, methyl-Enrichment, Kayla	

```
cd /home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_T3_3/NoSub_Soil_T3_3_megahit
head NoSub_Soil_T3_3_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' NoSub_Soil_T3_3_megahit.contigs.fa >NoSubSoilT33MC.fa

sed -i -e 's/>\(k.*\)/>NoSubSoilT33MC_\1/1' NoSubSoilT33MC.fa  #MC stands for Megahit_Contigs
```
**19, OWC_substrative_co_megahit_Deep.contigs.fa	1	OWC16 subtractive coassembly deep, assembly
```
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep
head OWC_substrative_co_megahit_Deep.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' OWC_substrative_co_megahit_Deep.contigs.fa >OwcDeepSubCoMC.fa

sed -i -e 's/>\(k.*\)/>OwcDeepSubCoMC_\1/1’ OwcDeepSubCoMC.fa  #MC stands for Megahit_Contigs
```
