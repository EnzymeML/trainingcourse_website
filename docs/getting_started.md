# Setup EnzymeML Lab and import chromatographic data

In this tutorial, we will install a computing environment with preinstalled tools and import and visualize chromatographic data. Then we will get the first example project from GitHub and run the analysis notebook of the project in your local JupyterLab environment.

## 1. Install Docker

In order to get a preconfigured computing environment, we will use Docker, which allows us to run JupyterLab on our local machine.
Visit the [Docker website](https://docs.docker.com/get-docker/) and follow the instructions for your operating system to install Docker.

??? info "What is Docker?"

    Docker is a way to run software in a container. This means that the software is isolated from the rest of your system. This is useful because it means that you can run software without having to install it on your system.

If you decide to configure your computing environment yourself you can install [ChromatoPy from Github](https://github.com/FAIRChemistry/chromatopy).

## 2. Install EnzymeML Lab

To work with Jupyter Notebooks, we will use the JupyterLab, which is a web-based interactive development environment for Jupyter notebooks, code, and data. We will use the EnzymeML Lab, which is a JupyterLab environment with preinstalled tools for the analysis of chromatographic data.

To install the EnzymeML Lab for the first time, follow the [instructions](jupyterlab_installation.md). This essentially starts a Docker container, which JupyterLab is running, and the developed tools of this course are preinstalled.

## 3. Load the demo project

Download the [demo project repository](https://github.com/FAIRChemistry/chromatography-example) from GitHub and store it at the desired location on your local machine. Click on the green "Code" button and select "Download ZIP". Finally, extract the ZIP file.

## 4. Open the project in JupyterLab

Go back to the browser in which JupyterLab is running and navigate to the folder of the demo project. Make sure, that the file is within the directory you defined to be visible to the container. You can now open the notebook `shimadzu-example.ipynb` or `single-chromatogram.ipynb` example and follow the instructions in the notebooks.
