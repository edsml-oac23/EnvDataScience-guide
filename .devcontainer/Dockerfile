# Base con conda/mamba preinstalado
FROM condaforge/mambaforge:latest

# Carpeta de trabajo
WORKDIR /workspaces/EnvDataScience-guide

# Copiamos el environment.yml
COPY environment.yml .

# Crear entorno con todo el stack geoespacial desde conda-forge
RUN mamba env create -f environment.yml && mamba clean -afy

# Activar el entorno por defecto en shells interactivos
SHELL ["/bin/bash", "-c"]
RUN echo "mamba activate eds-geospatial" >> /etc/bash.bashrc

# Usar un usuario existente del contenedor (evita el warning de $MAMBA_USER)
USER mamba
