FROM condaforge/mambaforge:latest

WORKDIR /workspaces/EnvDataScience-guide
COPY environment.yml .

# Build the geospatial environment
RUN mamba env create -f environment.yml && mamba clean -afy

# Auto-activate the environment for every shell
SHELL ["/bin/bash","-lc"]
RUN mamba init bash && echo "mamba activate eds-geospatial" >> /etc/bash.bashrc

# // Ideally, "mambuser" is the best practice. Probably ys permission issues in conda environment. 
USER root
