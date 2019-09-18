#16-Sept-2019

# virsorter to pick virus contigs out

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
cd /home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
scaffold.fa
screen -S virsorter_jordan_enrichment_idba_congits
/opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/virsorter-data
```

[liupf@zenith idba_assembled_output]$ /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/
Can't locate File/Which.pm in @INC (@INC contains: /opt/PfamScan /opt/PfamScan /opt/sas/lib /opt/sas/modules/lib/x86_64-linux-thread-multi /opt/sas/modules/lib /opt/sas/lib /opt/sas/modules/lib/x86_64-linux-thread-multi /opt/sas/modules/lib /usr/local/lib64/perl5 /usr/local/share/perl5 /usr/lib64/perl5/vendor_perl /usr/share/perl5/vendor_perl /usr/lib64/perl5 /usr/share/perl5 .) at /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl line 51.
BEGIN failed--compilation aborted at /opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl line 51.

##virsorter on zenith
```
source /opt/Miniconda2/miniconda2/bin/activate   virsorter
wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/virsorter-data

To deactivate the environment when done:
source /opt/Miniconda2/miniconda2/bin/deactivate
```
**1, **
**the enrichment culture of Jordan**
```
cd /home/projects/Wetlands/2014-2015_sampling/Methanogen_OWC_enrichment_2015/idba_assembled_output
scaffold.fa
screen -S virsorter_jordan_enrichment_idba_congits
/opt/VirSorter/wrapper_phage_contigs_sorter_iPlant.pl --fna scaffold.fa --db 2 --ncpu 4 --data-dir /opt/virsorter-data
```
