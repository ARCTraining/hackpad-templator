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

## Expected `config`

Each template expects a `config.yml` file to be committed within the branch to generate the hackpad. These just have to be simple
yml documents that specify the variables that jinja2 will fill in.

### HPC0

Expected yml file:

```yml
date:"2021-11"
```
