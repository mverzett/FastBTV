# FastBTV
Simple set of scripts and plugins for quick and fast BTV analysis

## Installation
```bash
cmsrel CMSSW_10_6_1_patch1
cd CMSSW_10_6_1_patch1/src/
cmsenv
git cms-init
#Get the latest DeepFlavour training
git cms-addpkg RecoBTag/Combined
git clone https://github.com/cms-data/RecoBTag-Combined.git RecoBTag/Combined/data

git clone git@github.com:panwarlsweet/FastBTV.git FastBTV/FastBTV
cd FastBTV/FastBTV/
git checkout eff_plots
cd ../..
scram b
```

## Usage
### Step 1 - make trees
```
cd FastBTV/FastBTV/run
./make_tree.py
```
**Warning!** The discriminators run, as well as the era, are hardcoded (at least for now).

### Step 2 - make the ROCs
```
./make_rocs.py OUTPUT_DIRECTORY [--bootstrap, to compute ROC uncertainties]
```
**Warning!** The discriminators plotted and the selection are hardcoded. This is specific decision as this 
package is intended for quick checks in specific topologies, rather then systematic studies. For those, please use
[BTagAnalyzer](https://github.com/cms-btv-pog/RecoBTag-PerformanceMeasurements/)
