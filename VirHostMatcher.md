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
# update 13-Nov-2019
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
```

#on unity, 
```
cd /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/host
touch Two_w_mcrA_methanoG.list
touch Anovio_cleaned_duplicated_remove.list
touch Anvio_cleaned_additional.list
#
cd /home/pengfei.2/OWC_dRep_3211_MAGs
#
cp /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/host/*Anvio*.fa ./

#
for file in  $(cat Two_w_mcrA_methanoG.list)
do 
cp ${file}.fa /home/pengfei.2/OWC_dRep_3211_MAGs
done 

#
cd /home/pengfei.2/OWC_dRep_3211_MAGs
for file in  $(cat /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/host/Anovio_cleaned_duplicated_remove.list)
do 
mv ${file}.fa /home/pengfei.2/
done
#mv O3C3D3_DDIG_MN_Anvio.967..fa O3C3D3_DDIG_MN_Anvio.967.fa
#

#creat work dir
cd ~
mkdir virHostMatcher_vOTU_3220MAGs
mv OWC_dRep_3211_MAGs virHostMatcher_vOTU_3220MAGs
cd virHostMatcher_vOTU_3220MAGs
mv OWC_dRep_3211_MAGs/ host
mv /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/virus ./
#4314 genomes


#python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b host -o output

cd /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_vOTUs_contigs
mv ../../*.fa ./

# this part is not finished due to limited wall time
```

#update 14-Nov-2019
```
#qsub scripts, only generate d2star metric
///
#PBS -l walltime=300:00:00
#PBS -l nodes=1:ppn=10,mem=40GB
#PBS -N VirHostMatcher
#PBS -m abe
#PBS -M liupf@colostate.edu

module use /fs/project/wrighton.1/scripts/modulefiles #W2 environment
module load load_scripts #W2 environment

cd /home/pengfei.2/virHostMatcher_vOTU4436_MAGs3220

python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b /home/pengfei.2/virHostMatcher_vOTU_3220MAGs/host -o output -d 1

#OWC_vOTUs_contigs -b OWC_MGdb89_genomes -o OWC_MGdb89_genomes_vOTUs_match

#qsub virHostMatcher.pbs
////
#grep -c '>' OWC_virsorter_10K_all_95-80.fna ;
# 4436 #update 14-Nov-2019
# but only 4410 virus genomes generate to match 3220 MAGs
#reasson for this: 4410 uniq names; 


#qstat 1425822
# done
```

#update on 23-Nov-2019
```
# Cluster_genomes_5.1.pl 
# after clustering, 26 duplicates sequences still exists???
```




#since no spacer matches the virus contigs, check the virhostmatcher
```
#

```
