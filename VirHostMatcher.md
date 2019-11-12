#virus match based on d2 matrix

#
```
#https://github.com/jessieren/VirHostMatcher

```

#spearate fasta file into one-seqs-per-file
```
#
#>VIRSorter
screen -S awk_split
awk '/^>VIRSorter/ {OUT=substr($0,2) ".fa"}; OUT {print >OUT}' OWC_virsorter_10K_all_95-80.fna 

#
```
## do not do this only on methanogens db, do it on all dRepped genomes
#
```

python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b host -o output

#virus dir :/home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_vOTUs_contigs


#host : check the genomes include all my Methanogen genomes
# replace those low quality with Anvio modified

cd /home/projects/Wetlands/All_genomes/OWC_MAGs_dRep_19Sept19/OWC_MAGs_19Sept19_dRep_/dereplicated_genomes
#1 copy all genomes to Unity  dereplicated_genomes_3211

#2 remove genomes with Anvio clean and add Anvio cleaned genomes back (total 20)
#Anvio-cleaned--part are in all dRep genomes, add all 20 Anvio clean genomes in, 
# remove not cleaned duplicates (13), 
#Anovio_cleaned_duplicated_remove.list  (13)
#Anvio_cleaned_additional.list (7 additional from MGdb to MG3211 db)


#3, Check renamed Methaongen genomes (5)

#4, check genomes with mcrA, not in dRep genomes, bring them back (2). 
#Two_w_mcrA_methanoG.list (from MGdb to MG3211 db)

#5 mismatch between all dRep with Methanogens only dRep (After adding 9 methanogen genomes, we have 3211+9 host to search)


/home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_MGdb89_genomes 
python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b host -o output

cd /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_vOTUs_contigs
mv ../../*.fa ./



```

#since no spacer matches the virus contigs, check the virhostmatcher
```
#
> length(unique(df_long_f$MAGs))
[1] 63
> length(unique(df_long_f$d2star))
[1] 200

63 MAGs had potential host-virus links to 200 virus contigs based on the virHostMatcher
```
