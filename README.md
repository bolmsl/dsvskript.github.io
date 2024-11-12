# DSP Script

Here you get know how to write a lecture script using Jupyter Book 2.0.

## Creating an Conda Environment

The conda environment is provided as `environment.yml`. This environment is used for all testing by Github Actions and can be setup by:

1. `conda env create -f environment.yml`
2. `conda activate DSP_Script (or the name of your own environment)`

## Building a Jupyter Book

Run the following command in your terminal:

```bash
jb build DSP_Script/
```

If you would like to work with a clean build, you can empty the build folder by running:

```bash
jb clean DSP_Script/
```

If jupyter execution is cached, this command will not delete the cached folder. 

To remove the build folder (including `cached` executables), you can run:

```bash
jb clean --all DSP_Script/
```


