# virus contigs dections on IDBA-UD scaffolds from Jordan's desertation

#sample list (6)
```
Mud_August_scaffold.fa	August Mud 2015 Assembly
OPEN_August_scaffold.fa	August Open 2015 Assembly
PLANT_August_scaffold.fa	August Plant 2015 Assembly
Nov_Mud_scaffold.fa	Nov Mud 2015 Assembly
Nov_plant_scaffold.fa	Nov Plant 2015 Assembly
Nov_open_scaffold.fa	Nov Open 2015 Assembly


```
#wkdir
```
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/Virus_metaG2014_15

```

#data-preparation
```
#1 Mud_August_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Aug_Mud_Surface/Mud_August_scaffold.fa -m 10000 > ./MudAugSca10K.fa
#2 OPEN_August_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Aug_Open_Surface/OPEN_August_scaffold.fa -m 10000 > ./OpenAugSca10K.fa
#3 PLANT_August_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Aug_Plant_Surface/PLANT_August_scaffold.fa -m 10000 > ./PlantAugSca10K.fa
#4 Nov_Mud_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Nov_Mud_Surface/Nov_Mud_scaffold.fa -m 10000 > ./MudNovSca10K.fa

#5 Nov_plant_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Nov_Plant_Surface/Nov_plant_scaffold.fa -m 10000 > ./PlantNovSca10K.fa

#6 Nov_plant_scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/Nov_Open_Surface/Nov_open_scaffold.fa -m 10000 > ./OpenNovSca10K.fa

#7, Mud_coassembly, scaffold.fa
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/coassemblies/Mud/scaffold.fa -m 10000 > MudCoSca10K.fa

#8
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/coassemblies/Open/scaffold.fa -m 10000 > OpenCoSca10K.fa

#9
pullseq -i /home/projects/Wetlands/2014-2015_sampling/MetaG/coassemblies/Plant/scaffold.fa -m 10000 > PlantCoSca10K.fa

```

#reformat each 10K scaffold fasta
```
cd /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/Virus_metaG2014_15

for file in *.fa
do 
echo "${file%.*}"
sed -i -e "s/>\(scaffold.*\)/>"${file%.*}"_\1/1" $file
done
```


```

screen -S virsorter_OWC2014_scaffold
source /opt/Miniconda2/miniconda2/bin/activate virsorter

for file in *.fa
do
echo "${file}"
wrapper_phage_contigs_sorter_iPlant.pl --wdir "${file%.*}" --fna ${file} --db 2 --ncpu 20 --data-dir /opt/virsorter-data
done
```

#collect cat1, 2, 4, and 5
```
for file in *.fa
do
cd "${file%.*}"/Predicted_viral_sequences/
echo "${file%.*}"
cat *_cat-1.fasta *_cat-2.fasta *_prophages_cat-4.fasta *_prophages_cat-5.fasta >> ../../OWC2014_virus_scaffold10K.fasta
#grep -c '>' *_cat-1.fasta *_cat-2.fasta *_prophages_cat-4.fasta *_prophages_cat-5.fasta 
cd ../../
done 
#336 sequences
```
#
for file in *.fa
do
cd "${file%.*}"/Predicted_viral_sequences/
echo "${file%.*}"
grep -c '>' *_cat-1.fasta *_cat-2.fasta *_prophages_cat-4.fasta *_prophages_cat-5.fasta 
cd ../../
done 


#add data to virsort_all_10K
```
https://github.com/liupfskygre/virus_in_metagenome/blob/master/vOTU_Virus_contigs_clustering.md

cat /home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/Virus_metaG2014_15/OWC2014_virus_scaffold10K.fasta >>/home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K/OWC_virsorter_10K_all.fa

#update 13-Nov-2019
#5769 +336 ==6105
```

#

