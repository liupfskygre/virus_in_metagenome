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
