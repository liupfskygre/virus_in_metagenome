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
python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b host -o output

#virus dir :/home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_vOTUs_contigs
#host : /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_MGdb89_genomes 
#python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v virus -b host -o output

cd /home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins/OWC_vOTUs_contigs
mv ../../*.fa ./

/home/pengfei.2/OWC_wetland_virsorter10K/OWC_MGdb89_bins

python /fs/byo/wrighton-data1/opt/VirHostMatcher/vhm.py -v OWC_vOTUs_contigs -b OWC_MGdb89_genomes -o OWC_MGdb89_genomes_vOTUs_match
 
```
