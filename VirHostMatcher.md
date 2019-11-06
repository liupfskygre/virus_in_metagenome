#virus match based on d2 matrix

#
```
https://github.com/jessieren/VirHostMatcher

```

#spearate fasta file into one-seqs-per-file
```
#
>VIRSorter

awk '/^>VIRSorter/ {OUT=substr($0,2) ".fa"}; OUT {print >OUT}' OWC_virsorter_10K_all.fa


```
