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

**8, Aug_N3_C1_D1_megahit_assembly	1	Aug_N3_C1_D1 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D1_reads_and_megahit_full_assembly/Aug_N3_C1_D1_megahit_assembly
head Aug_N3_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_N3_C1_D1_megahit.contigs.fa >AugN3C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugN3C1D1MC_\1/1' AugN3C1D1MC.fa  #MC stands for Megahit_Contigs
```

**9, Aug_N3_C1_D5_megahit_assembly	1	Aug_N3_C1_D5 Megahit full assembly**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_N3_C1_D5_reads_and_megahit_full_assembly/Aug_N3_C1_D5_megahit_assembly
head Aug_N3_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_N3_C1_D5_megahit.contigs.fa > AugN3C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugN3C1D5MC_\1/1' AugN3C1D5MC.fa  #MC stands for Megahit_Contigs

```

**10, Aug_OW2_C1_D1_megahit_assembly	1	Aug_OW2_C1_D1 Megahit full assembly**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D1_reads_and_megahit_full_assembly/Aug_OW2_C1_D1_megahit_assembly
head Aug_OW2_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_OW2_C1_D1_megahit.contigs.fa >AugOW2C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugOW2C1D1MC_\1/1' AugOW2C1D1MC.fa  #MC stands for Megahit_Contigs
```

**11, Aug_OW2_C1_D5_megahit_assembly	1	Aug_OW2_C1_D5 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_OW2_C1_D5_reads_and_megahit_full_assembly/Aug_OW2_C1_D5_megahit_assembly
head Aug_OW2_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_OW2_C1_D5_megahit.contigs.fa >AugOW2C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugOW2C1D5MC_\1/1' AugOW2C1D5MC.fa  #MC stands for Megahit_Contigs

```

**12, Aug_T1_C1_D1_megahit_assembly	1	Aug_T1_C1_D1 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D1_reads_and_megahit_full_assembly/Aug_T1_C1_D1_megahit_assembly
head Aug_T1_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_T1_C1_D1_megahit.contigs.fa >AugT1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>AugT1C1D1MC_\1/1' AugT1C1D1MC.fa  #MC stands for Megahit_Contigs
```

**13, Aug_T1_C1_D5_megahit_assembly	1	Aug_T1_C1_D5 Megahit full assembly**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/Aug_T1_C1_D5_reads_and_megahit_full_assembly/Aug_T1_C1_D5_megahit_assembly
head Aug_T1_C1_D5_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' Aug_T1_C1_D5_megahit.contigs.fa >AugT1C1D5MC.fa
sed -i -e 's/>\(k.*\)/>AugT1C1D5MC_\1/1' AugT1C1D5MC.fa  #MC stands for Megahit_Contigs
```

**14, May_M1_C1_D1_megahit_assembly	1	May_M1_C1_D1 Megahit full assembly**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D1_reads_and_megahit_full_assembly/May_M1_C1_D1_megahit_assembly
head May_M1_C1_D1_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D1_megahit.contigs.fa >MayM1C1D1MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D1MC_\1/1' MayM1C1D1MC.fa  #MC stands for Megahit_Contigs

```

**15, May_M1_C1_D3_megahit_assembly	1	May_M1_C1_D3 Megahit full assembl**

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D3_reads_and_megahit_full_assembly/May_M1_C1_D3_megahit_assembly
head May_M1_C1_D3_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D3_megahit.contigs.fa >MayM1C1D3MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D3MC_\1/1' MayM1C1D3MC.fa  #MC stands for Megahit_Contigs


```

**16, May_M1_C1_D6_megahit_assembly	1	May_M1_C1_D6 Megahit full assembly**	

```
cd /home/projects/Wetlands/2018_sampling/OWC_metaG_megahit/May_M1_C1_D6_reads_and_megahit_full_assembly/May_M1_C1_D6_megahit_assembly
head May_M1_C1_D6_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' May_M1_C1_D6_megahit.contigs.fa >MayM1C1D6MC.fa
sed -i -e 's/>\(k.*\)/>MayM1C1D6MC_\1/1' MayM1C1D6MC.fa  #MC stands for Megahit_Contigs
```
##
**17, NoSub_Soil_TF_1_megahit.contigs.fa	1	2018, methyl-Enrichment, Kayl**

```
cd /home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_TF_1/NoSub_Soil_TF_1_megahit
head NoSub_Soil_TF_1_megahit.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' NoSub_Soil_TF_1_megahit.contigs.fa > NoSubSoilTF1MC.fa
sed -i -e 's/>\(k.*\)/>NoSubSoilTF1MC_\1/1' NoSubSoilTF1MC.fa  #MC stands for Megahit_Contigs

```

**18, NoSub_Soil_T3_3_megahit.contigs.f 1	2018, methyl-Enrichment, Kayl**

```
cd /home/projects/Wetlands/2018_sampling/methyl_enrichment2018_metaG/NoSub_Soil_T3_3/NoSub_Soil_T3_3_megahit
head NoSub_Soil_T3_3_megahit.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' NoSub_Soil_T3_3_megahit.contigs.fa >NoSubSoilT33MC.fa

sed -i -e 's/>\(k.*\)/>NoSubSoilT33MC_\1/1' NoSubSoilT33MC.fa  #MC stands for Megahit_Contigs
```
##
**19, OWC_substrative_co_megahit_Deep.contigs.fa	1	OWC16 subtractive coassembly deep, assembly**
```
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep
head OWC_substrative_co_megahit_Deep.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' OWC_substrative_co_megahit_Deep.contigs.fa >OwcDeepSubCoMC.fa

sed -i -e 's/>\(k.*\)/>OwcDeepSubCoMC_\1/1' OwcDeepSubCoMC.fa  #MC stands for Megahit_Contigs

```

**20, OWC_substrative_co_megahit_Deep.contigs.fa	1	OWC16 subtractive coassembly surface, assembly**
```
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface
head OWC_substrative_co_megahit_Surface.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' OWC_substrative_co_megahit_Surface.contigs.fa >OwcSurfaceSubCoMC.fa

sed -i -e 's/>\(k.*\)/>OwcSurfaceSubCoMC_\1/1' OwcSurfaceSubCoMC.fa  #MC stands for Megahit_Contigs

```
##
**21, M3C5D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa	1	DDIG assembly from Marina, miller Lab**
```
cd /home/projects/Wetlands/All_genomes/DDIG_megahit_assemblies
head M3C5D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' M3C5D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa >M3C5D1DdigMC.fa
sed -i -e 's/>\(k.*\)/>M3C5D1DdigMC_\1/1' M3C5D1DdigMC.fa  #MC stands for Megahit_Contigs

```

**22 O3C3D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa	1	DDIG assembly from Marina, miller Lab**
```
cd /home/projects/Wetlands/All_genomes/DDIG_megahit_assemblies
head O3C3D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' O3C3D1_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa >O3C3D1DdigMC.fa
sed -i -e 's/>\(k.*\)/>O3C3D1DdigMC_\1/1' O3C3D1DdigMC.fa  #MC stands for Megahit_Contigs
```
**23 O3C3D3_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa	1	DDIG assembly from Marina, miller Lab**
```
cd /home/projects/Wetlands/All_genomes/DDIG_megahit_assemblies
head O3C3D3_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa

sed -e 's/>\(k.*\).*flag.*$/>\1/1' O3C3D3_DDIG_MN_megahit_k51_k121_s10_assembly.contigs.fa >O3C3D3DdigMC.fa
sed -i -e 's/>\(k.*\)/>O3C3D3DdigMC_\1/1' O3C3D3DdigMC.fa  #MC stands for Megahit_Contigs

```
**24 O3C3D4_DDIG_MN_megahit_assembly.contigs.fa	1	DDIG assembly from Marina, miller Lab**
```
cd /home/projects/Wetlands/All_genomes/DDIG_megahit_assemblies
head O3C3D4_DDIG_MN_megahit_assembly.contigs.fa
sed -e 's/>\(k.*\).*flag.*$/>\1/1' O3C3D4_DDIG_MN_megahit_assembly.contigs.fa >O3C3D4DdigMC.fa
sed -i -e 's/>\(k.*\)/>O3C3D4DdigMC_\1/1' O3C3D4DdigMC.fa  #MC stands for Megahit_Contigs

```

**25 M3C4D3_v1_scaffolds.fasta** 
```
cd /home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies
head M3C4D3_v1_scaffolds.fasta
#sed -e 's/>\(k.*\).*flag.*$/>\1/1' O3C3D4_DDIG_MN_megahit_assembly.contigs.fa >O3C3D4DdigMC.fa
sed -e 's/>\(scaffold.*\)/>M3C4D3v1MC_\1/1' M3C4D3_v1_scaffolds.fasta > M3C4D3v1MC_.fa
```
**26 M3C4D3_v2_scaffolds.fasta**
```
cd /home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies
head M3C4D3_v2_scaffolds.fasta 

sed -e 's/>\(scaffold.*\)/>M3C4D3v2MC_\1/1' M3C4D3_v2_scaffolds.fasta  > M3C4D3v2MC.fa
```
**27 M3C4D4_scaffolds.fasta**
```
cd /home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies
head M3C4D4_scaffolds.fasta 

sed -e 's/>\(scaffold.*\)/>M3C4D4MC_\1/1' M3C4D4_scaffolds.fasta  > M3C4D4MC.fa

```
**28 O3C3D3_scaffolds.fasta**
```

cd /home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies
head O3C3D3_scaffolds.fasta 

sed -e 's/>\(scaffold.*\)/>O3C3D3MC_\1/1' O3C3D3_scaffolds.fasta  > O3C3D3MC.fa
```
**29 O3C3D4_scaffolds.fasta
```
cd /home/projects/Wetlands/All_genomes/miller_lab_JGI_CSP_assemblies
head O3C3D4_scaffolds.fasta

sed -e 's/>\(scaffold.*\)/>O3C3D4MC_\1/1' O3C3D4_scaffolds.fasta  > O3C3D4MC.fa


```

**30
```
Enrichenment_2015_Jordan
cd /home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
scaffold.fa

# >scaffold_0 
sed -e 's/>scaffold_/>OwcEnrich2015IDBA_scaffold_/1' scaffold.fa > OwcEnrich2015IDBA.fa

```
