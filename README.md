# GOTM Testing Repo

Workplace for GOTM cases I am working on to help me better understand turbulent mixing in the ocean and write down lessons learned. To learn more about GOTM please have a look at the [homepage](https://gotm.net/portfolio/) and the GOTM [repo](https://github.com/gotm-model). 

## Installing GOTM

Installing GOTM has become quite easy compared to when I first started working with it in 2018. The installation can be now forked via conda. Here are the step-by-step instructions (MAC OS) I used, which follow the steps outlined [here](https://github.com/fabm-model/fabm/wiki/GOTM).

1. Install `brew` package manager for MacOS - see [instructions](https://brew.sh)
2. Install minconda: `brew install --cask miniconda`
3. Verify conda is installed `conda --version`
4. Install conda `conda create -n gotm -c conda-forge gotm`

### Optional steps

5. Check which python is currently installed (`which python`) in terminal
6. Install python manager `brew install pyenv` - read this helpful guide [here](https://realpython.com/intro-to-pyenv/) - its a great tool!
7. Follow guide to install python and set system default usying `pyenv`. You can type `pyenv -h` for instructions on how to set things up.
8. Verify pip installed `pip -V` and verify it matches the system default python installed. If not you may want to troubleshoot.
9. Once you have python and pip correctly installed install jupyter e.g. `pip install jupyter` 
10. Finally install any needed packages e.g. pandas, numpy, scipy


## Running GOTM

1. Go to terminal and activate the GOTM environment `conda activate gotm` this should change the operating environment from (base) to (gotm) in your shell.
2. Next navigate to the cases in this repo (e.g. `cd ~\gotm_case\Gotland_CaseStudy` and then run GOTM model by simply typing `gotm`
3. GOTM should run successfully, printing output to the terminal and then create an output file, in this case `gotland.nc`
4. You can now analyze the model output.
5. All settings related to the model run are contained in a single `gotm.yaml` file.


## Case 1: Gotland Deep

This is a standard experiment available on the GOTM homepage. There are several other [cases](https://gotm.net/portfolio/ocean/) as well that may be of interest to look at. The source code for the test cases is accessible [here](https://github.com/gotm-model/cases/tree/v6.0/gotland)

The python notebook shows a quick visualization of the case. Surface heat fluxes (loss) drives turbulent mixing in the winter due to buoyancy loss and vice versa. The case can be run for longer time periods if desired.

## Case 2: Labrador Sea 

This is a case I made for the location of the SeaCycler vertical profiler mooring using data from ERA5 renalysis and hydrographic profiles collected from ships along the AR7W line. 

The datasets used are:

- ERA5 Renalysis (SST, momentum, heat, short-wave radiation)
- Hydrographic CTD casts (T, S profiles)

The timespan of the data covers 2015-12-03 to 2017-11-20. The case is run for 1 year from 2016-07-01 to 2017-07-01 to look at winter mixing. This case can use improvement and updates. Only the top 500m are simulated as the interest is in the evolution of surface mixing. 

