# Start from a base image that has Mamba installed
FROM condaforge/mambaforge:latest

# Set the working directory inside the container
WORKDIR /workspaces/EnvDataScience-guide

# Copy the environment file into the container
COPY environment.yml .

# Create the conda environment from the .yml file
# This is the step that installs all geospatial libraries
RUN mamba env create -f environment.yml

# Activate the environment by default
SHELL ["/bin/bash", "-c"]
RUN echo "mamba activate eds-geospatial" >> /etc/bash.bashrc

# Set user to a non-root user for security
USER $MAMBA_USER