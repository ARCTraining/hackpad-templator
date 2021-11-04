# Research Computing Training Templater

This repository contains the code for a github action workflow that automatically generates a Hackmd hackpad for 
our training workshops using the hackmd-cli and jinja2 templates.

## Workflow

```
Create a new branch in this repo
containing a metadata file
            |
            |
            v
Github action detects the new branch and starts the action
            |  
            |
            v
Github action reads metadata file and uses variables to fill a jinja template
            |
            |
            v
This markdown file is then passed to hackmd-cli which imports the .md file as a new hackpad
```

## Usage

You can use this repository to automatically create a new Hackmd.io hackpad for Research Computing training sessions using templates included within this repo.

To create a new hackpad you need to create a branch with the format `<training-course-code>-yyyy-mm` for example for [HPC0](https://arc.leeds.ac.uk/training/courses/hpc0/) running in November 2021 you would create a branch `hpc0-2021-11`. You should then create a `config.yaml` file at the root of your repository containing values to be autofilled for the [template](#expected-config).

```bash
# example git command for creating a new branch
$ git checkout -b hpc0-2021-11
```

**After the hackpad is created you will still need to configure the hackpads sharing settings and edit the url slug of the hackpad which can be done via the hackmd.io interface.**

## Expected `config`

Each template expects a `config.yml` file to be committed within the branch to generate the hackpad. These just have to be simple
yml documents that specify the variables that jinja2 will fill in.

### HPC0 & HPC1

Expected yml file:

```yml
date: "2021-11" # specify the date to be included in the hackmd heading
morning: True # specify if the session is morning or not to control generated agenda timings
```
