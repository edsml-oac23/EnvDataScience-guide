# 1. Empezar desde la imagen base correcta de mambaforge
FROM condaforge/mambaforge:latest

# 2. Definir el directorio de trabajo
WORKDIR /workspaces/EnvDataScience-guide

# 3. Copiar el archivo de entorno
COPY environment.yml .

# 4. Crear el entorno usando Mamba (este es el paso lento)
RUN mamba env create -f environment.yml

# 5. Activar el entorno por defecto en el shell
SHELL ["/bin/bash", "-c"]
RUN echo "mamba activate eds-geospatial" >> /etc/bash.bashrc

# 6. Cambiar al usuario no-root correcto ('mambauser' para esta imagen)
USER mambauser