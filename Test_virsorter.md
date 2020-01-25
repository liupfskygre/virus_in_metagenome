#16-Sept-2019

# virsorter to pick virus contigs out
```
wrapper_phage_contigs_sorter_iPlant.pl --fna <sequences.fa> --db 2 --ncpu <cpu#>  
#key things
1, use --db 2
2, use blastp default
3, --virome, off, default one
4, --wdir         Working directory (DEFAULT cwd)
**1, **
**the enrichment culture of Jordan**
# 

```

```
cd /home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
scaffold.fa
screen -S virsorter_jordan_enrichment_idba_congits
/opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/virsorter-data
```
```
[liupf@zenith idba_assembled_output]$ /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/
Can't locate File/Which.pm in @INC (@INC contains: /opt/PfamScan /opt/PfamScan /opt/sas/lib /opt/sas/modules/lib/x86_64-linux-thread-multi /opt/sas/modules/lib /opt/sas/lib /opt/sas/modules/lib/x86_64-linux-thread-multi /opt/sas/modules/lib /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5 .) at /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl line 51.
BEGIN failed--compilation aborted at /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl line 51.
```
##virsorter on zenith
```
source /opt/Miniconda2/miniconda2/bin/activate   virsorter
wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 6 --data-dir /opt/virsorter-data

To deactivate the environment when done:
source /opt/Miniconda2/miniconda2/bin/deactivate
```
**1, **
**the enrichment culture of Jordan**
```
cd /home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
scaffold.fa

# >scaffold_0 
sed -e 's/>scaffold_/>OwcEnrich2015IDBA_scaffold_/1' scaffold.fa > OwcEnrich2015IDBA.fa

screen -r virsorter_jordan_enrichment_idba_congits
#4:19pm, 18Sept2019-

source /opt/Miniconda2/miniconda2/bin/activate   virsorter
wrapper_phage_contigs_sorter_iPlant.pl --fna OwcEnrich2015IDBA.fa --db 2 --ncpu 6 --data-dir /opt/virsorter-data & > OwcEnrich2015IDBA_virsorter.log
```

```
## Contig_id 1,Nb genes contigs2,Fragment3,Nb genes4,Category5,Nb phage hallmark genes6,Phage gene enrichment sig7,Non-Caudovirales phage gene enrichment sig8,Pfam depletion sig9,Uncharacterized enrichment sig10,Strand switch depletion sig11,Short genes enrichment sig12
```
Contig_id 1; Category, 5; 

**Notes**
```
what i usually do after that is import the viral counts to Geneious and then filter out anything that is less than 10kb except if it is circular, in which case i take it no matter what the size

1.0.5 on zenith #fixed the prophage issue in 1.0.3

```
