## this file documents the the specific and successful installation of TransposonUltimate as of 8/31/21, while that pipeline is still in preprint/review phase.

There are two steps here to isntall: conda environments and source installations

### FROM CONDA/MAMBA
```
# Environment 1 - including all annotation tools
conda create -y --prefix /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env
mamba install python=2.7
conda install -y -c bioconda repeatmodeler repeatmasker
mamba install -y -c bioconda genometools-genometools
mamba install -y -c derkevinriehl transposon_annotation_reasonate
mamba install -y -c derkevinriehl transposon_annotation_tools_proteinncbicdd1000
conda install -y -c derkevinriehl transposon_annotation_tools_transposonpsicli
mamba install -y -c derkevinriehl transposon_annotation_tools_mitetracker
mamba install -y -c derkevinriehl transposon_annotation_tools_sinescan=1.1.2
mamba install -y -c derkevinriehl transposon_annotation_tools_helitronscanner
mamba install -y -c derkevinriehl transposon_annotation_tools_mitefinderii
mamba install -y -c derkevinriehl transposon_annotation_tools_mustv2
mamba install -y -c derkevinriehl transposon_annotation_tools_sinefinder
mamba install -y -c anaconda biopython
conda activate

# Environment 2 - including CD-Hit and Transposon Classifier RFSB
conda create -y --prefix /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_reasonaTE
conda activate /gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_reasonaTE
mamba install -y -c anaconda biopython
mamba install -y -c bioconda cd-hit blast seqkit
mamba install -y -c derkevinriehl transposon_annotation_reasonate transposon_classifier_rfsb
conda activate
```






### FROM SOURCE

If you wanted update the repeatmasker library to use the full Dfam library, do the following:
```
#create specific conda env for repeatmasker installation only. this is needed because reasonaTE conda environements use python2, but updating Dfam library requires h5py and python3
mamba create --name repmasker_install h5py
source activate repmasker_install

#copy Dfam.h5 file into RepeatMasker/Libraries/

#go and configure RepeatMasker
cd RepeatMasker #
./configure

#when prompted, trf binary path is:
/gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env/bin/trf

#choose 3

#when prompted, hmmer binary path is:
/gpfs/home/ibishop/data/ibishop/condas/transposon_annotation_tools_env/bin

#choose 5
conda activate #which is best way to deactivate environment
```
