# conda without auto activation

After installing [mambaforge](https://github.com/conda-forge/miniforge) the choice of activating the base environment should be "no". Then execute

```
eval "$(/home/lo/mambaforge/bin/conda shell.bash hook)"
conda init
conda config --set auto_activate_base false
```

to be able to activate conda if desired. Otherwise it's not on the PATH.
