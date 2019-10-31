##


##
1, how to check virus from archaea 
```


```


2, virus contigs in each metaG 
```
# 
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith
mkdir OUT_virsorter_from_zenith

# rename tsv file and contigs file;  
# metaG.list

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

cat *VIRSorter_global-phage-signal.csv > OUT_zenith_VIRSorter_global-phage-signal.txt
awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' OUT_zenith_VIRSorter_global-phage-signal.txt >OUT_zenith_VIRSorter_global-phage-signal_hits.txt

```

#
```
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit


awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' VIRSorter_global-phage-signal.csv >VIRSorter_global-phage-signal_hits.csv
```
