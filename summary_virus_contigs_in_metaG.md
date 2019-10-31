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


##
grep -c '>' *.fasta #copy to excel file, 21420
grep -c '>' *cat-1.fasta 
grep -c '>' *cat-2.fasta 
grep -c '>' *cat-4.fasta 
grep -c '>' *cat-5.fasta 

```
