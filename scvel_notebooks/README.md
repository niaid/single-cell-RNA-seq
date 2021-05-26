To run scVelo on Locus, first you need to run Velocyto CLI.


module load samtools
samtools sort -t CB -O BAM -o cellsorted_possorted_genome_bam.bam possorted_genome_bam.bam
 
# velocyto CLI
module load python/3.7.3-foss-2016b
velocyto run10x yourcellrangerFolder /sysapps/cluster/software/cellranger/3.0.1/refdata-cellranger-mm10-1.2.0/genes/genes.gtf


After this, you will go to the notebooks to 
1. convert your seurate object, containing umap coordinates to a .loom format.(in R)
2. (in Python) integrate your umap coordinates from your Seurat to the integrated loom files generated.
3. (in Python) run steady-state model
4. (in Python) run the dynamic model
