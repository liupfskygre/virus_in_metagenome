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

#blast on all 10K virus contigs
```
sed -e 's/\(_gene_[0-9].*_gene_[0-9].*\)-.*-.*-cat_[0-9]$/\1/g' OWC_virsorter_10K_all.fa >OWC_virsorter_10K_all_fixed.fa
#sed -e 's/-/_/g' 
sed -i -e 's/\-/_/g' OWC_virsorter_10K_all_fixed.fa

sed -i -e 's/_circular/c_/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/__/_/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/gene/g/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/VIRSorter_//g' OWC_virsorter_10K_all_fixed.fa

makeblastdb -in OWC_virsorter_10K_all_fixed.fa -dbtype nucl -parse_seqids -out OWC_virsorter_10K

blastn -query OWC_MGdb_89_spacers196_6bins_fix.fasta -db OWC_virsorter_10K -outfmt 6 -max_target_seqs 5 -evalue 100 -num_threads 4 -out OWC_MGdb_89_spacers196_6bins_blastn_all10K.txt

#zero hits
```

#another two tries
## 1, with all non-dRep medium quality methanogens MAGs, detected the CRISPR spacer, then blastn to all virus contigs (before clustering)
```
# transfer 186 medium-high qua MAGs genomes from zenith to Mac
cd /Users/pengfeiliu/A_Wrighton_lab/Wetland_project/OWC_metaG_2014_2018/OWC_wetland_methanogens_database/MG_medium_quality178


#remove 8 Asgard genomes, but kept O3C3D4_DDIG_MN.839 (With mcrA as 474)
for file in Aug_M1C1D5_MC3a.78 O3C3D3_DDIG_MN.671 O3C3D3_DDIG_MN.740 O3C3D3_idba.40 O3C3D3_metabat_w_DDIG_2.5k.282 O3C3D4_DDIG_metabat.312 O3C3D4_DDIG_metabat.602 O3D3D3_DDIG_megahit.356
do
rm ${file}.fa
done
#

#use Geneious on 178 Medium-High qua genomes
#398 spacer were found in 178 genomes
# blastn to all virus contigs, 6105
sed -e 's/\(_gene_[0-9].*_gene_[0-9].*\)-.*-.*-cat_[0-9]$/\1/g' OWC_virsorter_10K_all.fa >OWC_virsorter_10K_all_fixed.fa
#sed -e 's/-/_/g' 
sed -i -e 's/\-/_/g' OWC_virsorter_10K_all_fixed.fa

sed -i -e 's/_circular/c_/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/__/_/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/gene/g/g' OWC_virsorter_10K_all_fixed.fa
sed -i -e 's/VIRSorter_//g' OWC_virsorter_10K_all_fixed.fa

awk '/^[>;]/ { if (seq) { print seq }; seq=""; print } /^[^>;]/ { seq = seq $0 } END { print seq }' OWC_virsorter_10K_all_fixed.fa > OWC_virsorter_10K_all_fixed_lin.fa

#fastx_collapser -i OWC_virsorter_10K_all_fixed_lin.fa -o OWC_virsorter_10K_all_fixed_col.fa
#remove duplicate seqs, bbmap tools
dedupe.sh in=OWC_virsorter_10K_all_fixed_lin.fa out=OWC_virsorter_10K_all_fixed_col.fa
#5758
makeblastdb -in OWC_virsorter_10K_all_fixed_col.fa -dbtype nucl -parse_seqids -out OWC_virsorter_10K


sed -e 's/_-_CRISPR_[0-9];_//g' Spacer398annotations.fasta > Spacer398annotations_fixed.fasta

blastn -query Spacer398annotations_fixed.fasta -db OWC_virsorter_10K -outfmt 6 -max_target_seqs 5 -evalue 100 -num_threads 4 -out Spacer398annotations_fixed_blastn_all10K.txt

#still zero hits. 
```

## 2, use CRISPR from dRep MAGs to blastn all virus contigs (the way above also covered this)



