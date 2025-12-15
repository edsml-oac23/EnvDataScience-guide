FROM condaforge/mambaforge:latest

WORKDIR /workspaces/EnvDataScience-guide
COPY environment.yml .

# Install the environment
RUN mamba env create -f environment.yml && mamba clean -afy

# Create non-root user (standard VS Code devcontainer practice)
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo "$USERNAME ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Auto-activate conda env for the non-root user
USER $USERNAME
RUN mamba init bash \
    && echo "mamba activate eds-geospatial" >> ~/.bashrc