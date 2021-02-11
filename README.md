# Machine Learning nbdev template
> Template for development of machine learning packages using nbdev


Clone this repository to start any new project or package development

# Install

## Activate conda environment

Run

```
conda deactivate
conda create --name nbdev
conda activate nbdev
```

Now install nbdev and fastcore

```
pip install nbdev
pip install fastcore
```

### Additional environments

Download ymls from envs directory in https://github.com/asrishaheem/segmentation/ 

* This contains envs directory with some yaml files
* These will create an env called nbdev (change as needed
* Previously, it was found that nbdev is better stalled using pip


```
conda env update --file envs/ml-base.yml
conda env update --file envs/jupyter.yml
```

    
And choose from the following as needed

```
conda env update --file envs/pytorch.yml
conda env update --file envs/mlflow.yml
conda env update --file envs/tensorflow.yml
conda env update --file envs/dvc.yml
```

And activate the environment

```
conda activate nbdev
```

Ensure reccomended jupyter extensions are enabled

```
jupyter nbextensions_configurator enable --user
jupyter contrib nbextension install --user
jupyter notebook
```

Navigate to [nbextensions](http://localhost:8888/nbextensions) and check that Table of Contents 2 and collapsable headings are enabled.

Exit jupyter notebook (CTRL+C)



## Create new nbdev project

* Note the project name "new_project" must only use underscore and must not begin with a number
* Basically, you should be able to name a python variable with this string

```
conda activate nbdev
```


```
cd root/directory/for/new_project
nbdev_new new_project
cd new_project
```


## Edit settings.ini

```
code .
```

Change the following 
* Make sure th change lib_name to the name of the new project
* Replace all between user and branch as follows

```
[DEFAULT]
lib_name = new_project
user = asrishaheem
description = asrishaheem
keywords = asrishaheem
author = asrishaheem
author_email = asrishaheem@gmail.com
copyright = asrishaheem
branch = master
conda_requirements = numpy

```

## Create new repository on github

```
gh repo create new_project
```

* Select private
* Y

Make first commit

```
git add .
git commit -m "First commit"
git push --set-upstream origin master
```

## Set up project

### Housekeeping (needed on my pc)

```
mkdir ./docs/_data
sed -i 's/your_lib/new_project/g' index.ipynb
```

### Install webhooks

```
nbdev_install_git_hooks
```

### Run nbdev tests

```
nbdev_build_lib
nbdev_update_lib
nbdev_test_nbs
nbdev_read_nbs
nbdev_build_docs
```

### Trouble shoot


If build docs fails try:

```
pip uninstall nbdev
pip install nbdev
```

If it still fails try

```
conda remove nbconvert
conda install nbconvert=5.6.1
```

### Check that project installs

```
pip install -e .
```

## Run jupyter

```
jupyter notebook
```

* Log into notebook (might be serving at different port than 8888 if another jupyter is arleady running)

* Edit/create new packages as needed

```
hello_world()
```

    Hello World
    
