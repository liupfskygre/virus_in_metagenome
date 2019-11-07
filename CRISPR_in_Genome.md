#
#export spacer from genious (repeats+spacers==CRISPR units in geneious) #after this, blastn spacer to vContigs

# with the vOTU, we could do blastn to search spacer with vContigs
```
#add file name to contigs
for file in *fa
do 
var="${file%.*}"
echo $var
sed -e "s/>\(.*\)/>"$var"_\1/g" $file >"${file%.*}"_rename.fasta
done

```

#in geneious, get all spacers
```
#/home/projects/Wetlands/All_genomes/OWC_viral_from_metaG/OWC_virsorter_10K

#fix header
sed -e 's/-/_/g' OWC_virsorter_10K_all_95-80.fna >OWC_virsorter_10K_all_95_80_fix.fna
sed -i -e 's/\(_gene_[0-9].*\)_gene.*cat/\1_cat/g' OWC_virsorter_10K_all_95_80_fix.fna
sed -i -e 's/_circular/c_/g' OWC_virsorter_10K_all_95_80_fix.fna
sed -i -e 's/cat//g' OWC_virsorter_10K_all_95_80_fix.fna
sed -i -e 's/gene/g/g' OWC_virsorter_10K_all_95_80_fix.fna

makeblastdb -in OWC_virsorter_10K_all_95_80_fix.fna -dbtype nucl -parse_seqids -out OWC_virsorter_10K_all_vOTU

sed -e 's/_-_CRISPR_[0-9];_//g' OWC_MGdb_89_spacers196_6bins.fasta > OWC_MGdb_89_spacers196_6bins_fix.fasta

screen -S blastn
blastn -query OWC_MGdb_89_spacers196_6bins_fix.fasta -db OWC_virsorter_10K_all_vOTU -outfmt 6 -max_target_seqs 5 -evalue 100 -num_threads 4 -out OWC_MGdb_89_spacers196_6bins_blastn.txt

#blast returns no results??

```
