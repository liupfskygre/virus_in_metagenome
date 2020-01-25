##


##
1, how to check virus from archaea 
```


```


2, virus contigs in each metaG, zenith
```
# 
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith
mkdir OUT_virsorter_from_zenith

# rename tsv file and contigs file;  
# metaG.list

####
for file in $(cat metaG.list)
do 
cd "${file}"_virsorter-out
cp VIRSorter_global-phage-signal.csv /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/"${file}"_VIRSorter_global-phage-signal.csv
cd Predicted_viral_sequences
cp VIRSorter_cat-1.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/"${file}"_VIRSorter_cat-1.fasta
cp VIRSorter_cat-2.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/"${file}"_VIRSorter_cat-2.fasta
cp VIRSorter_prophages_cat-4.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/"${file}"_VIRSorter_prophages_cat-4.fasta
cp VIRSorter_prophages_cat-5.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/"${file}"_VIRSorter_prophages_cat-5.fasta
cd ../../
done
#

##
cat *VIRSorter_global-phage-signal.csv > OUT_zenith_VIRSorter_global-phage-signal.txt
awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' OUT_zenith_VIRSorter_global-phage-signal.txt >OUT_zenith_VIRSorter_global-phage-signal_hits.txt

#cat OUT_zenith_VIRSorter_global-phage-signal_hits.txt|wc -l
13240


##
grep -c '>' *.fasta #copy to excel file, 13240
grep -c '>' *cat-1.fasta 
grep -c '>' *cat-2.fasta 
grep -c '>' *cat-4.fasta 
grep -c '>' *cat-5.fasta 

```
##two co-assembly
```
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Deep/virsorter-out
cp VIRSorter_global-phage-signal.csv ../../OWC_subtractive_megahit_coassembly_virsorter_OUT/OwcDeepSubCoMC_VIRSorter_global-phage-signal.csv

cd Predicted_viral_sequences/

cp VIRSorter_cat-1.fasta ../../../OWC_subtractive_megahit_coassembly_virsorter_OUT/OwcDeepSubCoMC_VIRSorter_cat-1.fasta
cp VIRSorter_cat-2.fasta ../../../OWC_subtractive_megahit_coassembly_virsorter_OUT/OwcDeepSubCoMC_VIRSorter_cat-2.fasta
cp VIRSorter_prophages_cat-4.fasta ../../../OWC_subtractive_megahit_coassembly_virsorter_OUT/OwcDeepSubCoMC_VIRSorter_prophages_cat-4.fasta
cp VIRSorter_prophages_cat-5.fasta ../../../OWC_subtractive_megahit_coassembly_virsorter_OUT/OwcDeepSubCoMC_VIRSorter_prophages_cat-5.fasta 


awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' OwcDeepSubCoMC_VIRSorter_global-phage-signal.csv > OwcDeepSubCoMC_VIRSorter_global-phage-signal_hits.txt

cat OwcDeepSubCoMC_VIRSorter_global-phage-signal_hits.txt|wc -l
#

grep -c '>' *.fasta #copy to excel file, 13240
grep -c '>' *cat-1.fasta 
grep -c '>' *cat-2.fasta 
grep -c '>' *cat-4.fasta 
grep -c '>' *cat-5.fasta 


#
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface/virsorter-out


```

#3, summit
```
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit

mkdir OUT_virsorter_from_summit
/home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit
# rename tsv file and contigs file;  
# metaG.list, remove metaG from 2018, which has being done on zenith

####
for file in $(cat metaG.list)
do 
cd "${file}"
cp VIRSorter_global-phage-signal.csv /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/"${file}"_VIRSorter_global-phage-signal.csv
cd Predicted_viral_sequences
cp VIRSorter_cat-1.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/"${file}"_VIRSorter_cat-1.fasta
cp VIRSorter_cat-2.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/"${file}"_VIRSorter_cat-2.fasta
cp VIRSorter_prophages_cat-4.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/"${file}"_VIRSorter_prophages_cat-4.fasta
cp VIRSorter_prophages_cat-5.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/"${file}"_VIRSorter_prophages_cat-5.fasta
cd ../../
done
#

##
cat *VIRSorter_global-phage-signal.csv > OUT_summit_VIRSorter_global-phage-signal.txt

awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' OUT_summit_VIRSorter_global-phage-signal.txt>OUT_summit_VIRSorter_global-phage-signal_hits.txt

cat OUT_summit_VIRSorter_global-phage-signal_hits.txt|wc -l
#21420
grep -c 'VIRSorter' VIRSorter_summit_lenght_summary.txt
21416


##
grep -c '>' *.fasta #copy to excel file, 21420
grep -c '>' *cat-1.fasta 
grep -c '>' *cat-2.fasta 
grep -c '>' *cat-4.fasta 
grep -c '>' *cat-5.fasta 

```

#get the length of each genes 
```
#
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit
#
for file in $(cat ../metaG.list)
do 
contig_stats.pl -i "${file}"_VIRSorter_cat-1.fasta -o "${file}"_VIRSorter_cat-1_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_cat-2.fasta -o "${file}"_VIRSorter_cat-2_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_prophages_cat-4.fasta -o "${file}"_VIRSorter_prophages_cat-4_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_prophages_cat-5.fasta -o "${file}"_VIRSorter_prophages_cat-5_stats -min_length 1
done

#sovle devided by 0 
#contig_stats.pl -i OwcEnrich2015IDBA_VIRSorter_prophages_cat-5.fasta -o OwcEnrich2015IDBA_VIRSorter_prophages_cat-5_stats -min_length 1
ls -alhS *.fasta|wc -l
#48
#8 have 0 hits

for file in $(cat ../metaG.list)
do 
grep 'VIRSorter' "${file}"_VIRSorter_cat-1_stats.summary.txt > "${file}"_VIRSorter_cat-1_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_cat-2_stats.summary.txt > "${file}"_VIRSorter_cat-2_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_prophages_cat-4_stats.summary.txt > "${file}"_VIRSorter_prophages_cat-4_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_prophages_cat-5_stats.summary.txt > "${file}"_VIRSorter_prophages_cat-5_stats_hits.txt
done

cat *_stats_hits.txt > VIRSorter_summit_lenght_summary.txt

cat *cat-1_stats_hits.txt >VIRSorter_summit_lenght_summary_cat-1.txt
cat *cat-2_stats_hits.txt >VIRSorter_summit_lenght_summary_cat-2.txt
cat *cat-4_stats_hits.txt >VIRSorter_summit_lenght_summary_cat-4.txt
cat *cat-5_stats_hits.txt >VIRSorter_summit_lenght_summary_cat-5.txt
#VIRSorter_summit_lenght_summary.txt
#21416 VIRSorter_summit_lenght_summary.txt

##summary of numbers
# cat OUT_summit_VIRSorter_global-phage-signal_hits.txt|wc -l
#21420
grep -c 'VIRSorter' VIRSorter_summit_lenght_summary.txt
21416??
#from fasta adds up
#21420


##zenith
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith
#12 have 0 hits 
#do contigs.pl as above
cat *_stats_hits.txt > VIRSorter_zenith_lenght_summary.txt

cat *cat-1_stats_hits.txt >VIRSorter_zenith_lenght_summary_cat-1.txt
cat *cat-2_stats_hits.txt >VIRSorter_zenith_lenght_summary_cat-2.txt
cat *cat-4_stats_hits.txt >VIRSorter_zenith_lenght_summary_cat-4.txt
cat *cat-5_stats_hits.txt >VIRSorter_zenith_lenght_summary_cat-5.txt

#13240 VIRSorter_zenith_lenght_summary.txt
```
##OwcDeepSubCoMC
##
```
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_subtractive_megahit_coassembly_virsorter_OUT
OwcDeepSubCoMC_
#
for file in OwcDeepSubCoMC
do 
contig_stats.pl -i "${file}"_VIRSorter_cat-1.fasta -o "${file}"_VIRSorter_cat-1_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_cat-2.fasta -o "${file}"_VIRSorter_cat-2_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_prophages_cat-4.fasta -o "${file}"_VIRSorter_prophages_cat-4_stats -min_length 1
contig_stats.pl -i "${file}"_VIRSorter_prophages_cat-5.fasta -o "${file}"_VIRSorter_prophages_cat-5_stats -min_length 1
done

ls -alhS *.fasta|wc -l
#48
#8 have 0 hits

for file in OwcDeepSubCoMC
do 
grep 'VIRSorter' "${file}"_VIRSorter_cat-1_stats.summary.txt > "${file}"_VIRSorter_cat-1_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_cat-2_stats.summary.txt > "${file}"_VIRSorter_cat-2_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_prophages_cat-4_stats.summary.txt > "${file}"_VIRSorter_prophages_cat-4_stats_hits.txt
grep 'VIRSorter' "${file}"_VIRSorter_prophages_cat-5_stats.summary.txt > "${file}"_VIRSorter_prophages_cat-5_stats_hits.txt
done

cat *_stats_hits.txt > VIRSorter_OwcDeepSubCoMC_lenght_summary.txt

cat *cat-1_stats_hits.txt >VIRSorter_OwcDeepSubCoMC_lenght_summary_cat-1.txt
cat *cat-2_stats_hits.txt >VIRSorter_OwcDeepSubCoMC_lenght_summary_cat-2.txt
cat *cat-4_stats_hits.txt >VIRSorter_OwcDeepSubCoMC_lenght_summary_cat-4.txt
cat *cat-5_stats_hits.txt >VIRSorter_OwcDeepSubCoMC_lenght_summary_cat-5.txt

#grep -c 'VIRSorter' VIRSorter_OwcDeepSubCoMC_lenght_summary.txt
# 5238

VIRSorter_OwcDeepSubCoMC_lenght_summary.txt


```


#transfer to MAC and chage format
```
cat VIRSorter_OwcDeepSubCoMC_lenght_summary.txt VIRSorter_summit_lenght_summary.txt VIRSorter_zenith_lenght_summary.txt > VIRSorter_OWC_lenght_summary.txt

sed -i -e 's/[0-9]*\. //1' VIRSorter_OWC_lenght_summary.txt
sed -i -e 's/-circular//1' VIRSorter_OWC_lenght_summary.txt
sed -i -e 's/_gene.*-cat/-cat/1' VIRSorter_OWC_lenght_summary.txt
sed -e 's/_/\t/1' VIRSorter_OWC_lenght_summary.txt >VIRSorter_OWC_lenght_summary_fix.txt
sed -i -e 's/-/\t/1' VIRSorter_OWC_lenght_summary_fix.txt
sed -i -e 's/_/\t/1' VIRSorter_OWC_lenght_summary_fix.txt

VIRSorter_MayM1C1D6MC_

```


#virsorter 10K contigs output
```
#from zenith
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/
for file in *.fasta
do 
pullseq -i ${file} -m 10000 > "${file%.*}"_10K.fasta
done 

#move to this folder
mkdir virsorter_10K_zenith
/home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/virsorter_10K_zenith

##two additional co-assembly 
cd /home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_subtractive_megahit_coassembly_virsorter_OUT
#pull 10K
mv *_10K.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/virsorter_10K_zenith

#surface
/home/projects/Wetlands/All_genomes/OWC_subtractive_megahit_coassembly/OWC_substrative_co_megahit_Surface/virsorter_co_megahit_Surface_10K/Predicted_viral_sequences

mv *1_10K.fasta /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith/OUT_virsorter_from_zenith/virsorter_10K_zenith
mv *2_10K.fasta 
mv *4_10K.fasta 
mv *5_10K.fasta 
#


#from summit
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit

#10K
for file in *.fasta
do 
pullseq -i ${file} -m 10000 > "${file%.*}"_10K.fasta
done 

mkdir virsorter_10K_summit
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit/OUT_virsorter_from_summit/virsorter_10K_summit



```
#All_genomes
```
#OWC_metaG_virsorter_10K
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K

#with all 30 metaG, 10K virsorter output here. 
5769
```

#adding  virus from Jordan 2014-2015 desertation
```
https://github.com/liupfskygre/virus_in_metagenome/blob/master/virsorter_Jordan_desertation_metaG.md

cat /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/Virus_metaG2014_15/OWC2014_virus_scaffold10K.fasta >>/home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K/OWC_virsorter_10K_all.fa

#update 13-Nov-2019
#5769 +336 ==6105
OWC_virsorter_10K_all.fa 

#
#move to generate vOTU by 95-80 cutoff by Cluster_genomes_5.1.pl, 

#then vConTACT2_0.9.8 on vOTU to generate vOTU clusters and tax classification
```



