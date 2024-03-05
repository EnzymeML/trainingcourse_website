---
icon: simple/jupyter
---

# Setting up JupyterLab

!!! info
    __What is JupyterLab?__  
    JupyterLab is a web-based editor for writing and executing Jupyter Notebooks. Additionally, it allows you to see the file system, terminal, and other tools in the same window. This makes it a powerful tool for data analysis and visualization.

    __How does it work?__  
    Here we will install JupyterLab using Docker. This will allow you to run JupyterLab on your local machine without having to install Python, Jupyter, and the necessary Python tools to work with your data and the tools developed in this course.
    Essentially, the Docker hosts a local website on your computer that runs JupyterLab. This website is accessible from your web browser as long as the container is running. Each time you start the container, the latest versions of the EnzymeML tools will be installed.

## Initial Setup

1. Install [Docker]
  [Docker]: docker_installation.md

2. Open the Docker Desktop application search for `haeussma/enzymeml-lab` in the upper search bar and click on `Pull`.

    ![Docker Desktop](../figs/get_image.png){{: style="height:400px"}}
    
3. Navigate to the `Images` section in the Docker Desktop application and click on :material-play: next to the `haeussma/enzymeml-lab` image.
    A `Run a new container` window pops up. Click on `Optional settings` to configure the container with the following settings:

    `Container name`
    :   Container name: `EnzymeML-Lab`

    `Ports`
    :    Host port: `8888`

    `Volumes` 
    !!! info inline end "Why specify a volume?"
        The volume is used to define what directory of your local machine is visible to the container. Without this configuration, the container would not be able to access your local files. It is advised to make the directory in which you store your data for analysis.


    :   Host path: `{SELECT YOUR WORKING DIRECTORY}`       
    :    Container path: `/home/jovyan/work`

    ??? example "Example"
        ![Docker Desktop](../figs/configure_container.png){: style="height:400px"}


    Then, click on `Run`. The initial configuration process for the container might take a few seconds up to two minutes.


5. Click on the link `8888:8888` in the header of the container. This will open a new tab in your browser, showing the JupyterLab environment.
    
    ![Docker Desktop](../figs/initial_start.png){{: style="height:400px"}}


7. 🎉 You are now in the JupyterLab environment. Your local files can be accessed via the `work` folder.

## Stopping the Container

To start the container, navigate to the `Containers` section in the Docker Desktop application and click on the :material-stop: button next to the `EnzymeML-Lab` container. Running containers are symbolized by a green container icon. You can close the browser window whenever you want. The container will keep running in the background unless you stop it in the Docker Desktop app.

## Restarting the Container

To start the container, navigate to the `Containers` section in the Docker Desktop application and click on the :material-play: button next to the `EnzymeML-Lab` container. Then click on the blue port number `8888:8888` next to the start button.