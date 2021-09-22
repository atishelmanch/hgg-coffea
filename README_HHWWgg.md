# hgg-coffea HHWWgg development

The purpose of this readme is to document some setup steps used for HH->WWgg tagger development.

Running on coffea-casa: https://cmsaf-jh.unl.edu/hub/spawn

```
git clone git clone git@github.com:atishelmanch/hgg-coffea.git -b HHWWgg_Tagger
cd hgg-coffea
pip install -e . ##-- Use src/ files as source for hgg_coffea class for development
python3 runner.py  --samples HHWWgg_1File.json --wf dystudies --meta Era2017_RR-31Mar2018_v1.json --ts HHWWggTagger --output test --dump .
python3 runner.py  --samples HHWWgg_dataset.json --wf dystudies --meta Era2017_RR-31Mar2018_v1.json --ts HHWWggTagger --output test --dump .
python3 runner.py  --samples HHWWgg_dataset.json --wf dystudies --executor dask/casa --chunk=500000 --scaleout 1 --skipbadfiles --limit 2 --meta Era2017_RR-31Mar2018_v1.json --ts HHWWggTagger --output test --dump .
```

before committing:

```
pip install pre-commit
pre-commit run --all-files
```

To change file permissions to file creator only:

```
chmod 600 filename
```
