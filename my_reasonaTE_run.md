## Basic outline of usage of reasonaTE


### create a project
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
mkdir workspace
reasonaTE -mode createProject -projectFolder workspace -projectName ref_euk -inputFasta ref_euk.fa
```

### annotate with different tools
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool helitronScanner
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool ltrHarvest
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool mitefind
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool mitetracker
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool must #having trouble with this one
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool repeatmodel
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool repMasker
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool sinefind
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool sinescan
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool tirvish
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool transposonPSI
reasonaTE -mode annotate -projectFolder workspace -projectName ref_euk -tool NCBICDD1000
```

### check annotation tools process
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
reasonaTE -mode checkAnnotations -projectFolder workspace -projectName ref_euk
```

### parse annotations, combine them/translate them behind the scenes
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
reasonaTE -mode parseAnnotations -projectFolder workspace -projectName ref_euk
```

### run pipeline and statistics
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_reasonaTE
reasonaTE -mode pipeline -projectFolder workspace -projectName ref_euk

reasonaTE -mode statistics -projectFolder workspace -projectName ref_euk
```

### rename seq in output annotation files, back to original contig strings

still working this part out
```
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_reasonaTE
reasonaTE -mode sequenceRenamer -projectFolder workspace -projectName ref_euk
```















