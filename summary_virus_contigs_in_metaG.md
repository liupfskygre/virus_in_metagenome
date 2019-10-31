##


##
1, how to check virus from archaea 
```


```


2, virus contigs in each metaG 
```
# 
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_zenith

#
cd /home/projects/Wetlands/OWC_viral_from_metaG/virsorter_from_summit


awk -F ',' '$5==1||$5==2||$5==4||$5==5 {print $0}' VIRSorter_global-phage-signal.csv >VIRSorter_global-phage-signal_hits.csv
```
