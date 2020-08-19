#cyverse vOTU clustering

#update
```
using -c 85, -i 95 as 

#all new update by Reb are here
/home/projects/across_ecosystems_viral_04_2020/OWC_only/OWC_all_unclustered_viruses_051920_95-85.clstr

6,716 viruses after clustering!
Fasta is: OWC_all_unclustered_viruses_051920_95-85.fna

Sometimes VirSorter trims a prophage to under 10 kb
Now have 6645 viral contigs. Use this file: OWC_viral_clustered_95_85_10kb_060420.fasta   One is almost 300kb!
```


#Viruses_Pengfei_11_1_19.docx

#ClusterGenomes’ (v 1.1.3) app in CyVerse using the parameters 95% average nucleotide identity and 80% alignment fraction of the smallest contig. 
#Ref: Daly, 2018

#https://de.cyverse.org/de/, cyverse discovery environments

#ClusterGenomes

```
#upload data to cyverse

# md5 OWC_virsorter_10K_all 1e562623e9c486ab073f9ae49c7da2a1

#
```

#this could be done on zenith
```
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K

screen -S cluster_genome
OWC_virsorter_10K_all.fa
# Cluster_genomes_5.1.pl -f input.fa -c 80 -i 95 -t 2

#update 13-Nov-2019
Cluster_genomes_5.1.pl -f OWC_virsorter_10K_all.fa -c 80 -i 95 -t 6

grep -c '>' OWC_virsorter_10K_all_95-80.fna
#4313 ==>4436 #update 13-Nov-2019

```
#export spacer from genious (repeats+spacers==CRISPR units in geneious)
#after this, blastn spacer to vContigs
```
# with the vOTU, we could do blastn to search spacer with vContigs

```

#transfer the vOTU and  MGDB89 to unity to run virHostMatcher
```
#0.25 cutoff
OWC_virsorter_10K_all_95-80.fna 
#https://github.com/liupfskygre/virus_in_metagenome/edit/master/VirHostMatcher.md
```
