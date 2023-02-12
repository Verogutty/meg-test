Nouveau fichier pour les analyse de chip_seq
## Methodology
finding the most likely binding sites involves the following steps:

## 1)Perform correlation studies by means of ChIP-Cor 
to estimate the average fragment length of the ChIP-Seq data under study, and to estimate the average background count density. ChIP-Cor generates a positional correlation plot for two features that may be '+' and '-' strand tags from the same experiment:
        -5'-3' tag correlation is used for fragment length 
         estimation and consequently for tag centering;
        -autocorrelation analysis reveals the density of peaks 
         that represent binding compare to the average 
         background density. The average background density is then used to estimate a reasonable threshold for 
         binding peaks.

![alt text for screen readers](PG1.PNG)
         
         
## 2)Shift tags mapping to the + or - strand towards the expected center of the DNA fragment by ChIP-Center 
to generate a SGA file containing centered tags. The shif amount is half the average fragment lenght.

![alt text for screen readers](SG2.PNG)
[File Containing Centered Tags](stat1_th15.sga)//
[Refinement of peak centers](Rescoring.sga)

## 3)Find putative binding peaks by ChIP-Peak using the centered ChIP-Seq tags.
   Use regions of the genomes with low density reads as 
   estimated background (ChIP-Cor).
   ChIP-Peak determines a cumulative tag count in a  
   specified window of width w (in bp).
       