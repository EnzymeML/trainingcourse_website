# Process Plate Reader Data

In this hackathon session, you will process your own plate reader data using the `mtphandler` Python package. Alternatively, if you do not have your own data, or something fails, you can use the provided example data.

## 📚 Topics

1. You will get familiar with using Jupyter Notebooks and how you can run Python code locally on your computer.
2. You will learn how to process and enrich you plate reader data using the `mtphandler` Python package.
3. You will yield a structured EnzymeML Document that can be used for further data analysis.

## 🛠️ Setup

### Start Jupyter Notebook
Start with opening Anaconda and launching a Jupyter Notebook. If this is the first time you ever used a Jupyter Notebook, you can find a short introduction [:simple-youtube: here](https://youtu.be/IMrxB8Mq5KU?si=UdcbsNZYd2S-Geg6&t=64). Otherwise, you can skip this step.

### Setup a project folder and notebook
Navigate to your desired location and create a new folder for your project. This folder will contain all the files you will create during this session.
Afterwards, create a new Jupyter Notebook in this folder. You can create new folders and the notebook directly from the Jupyter Notebook interface. Therefore, you can use the `New`:octicons-triangle-down-16: button in the top right corner and select `Folder` or `Notebook Python3 (ipykernel)`.

### Add the data to your project folder
If you brought your own plate reader file, add it to the project folder. If you do not have your own data, you can <a href="https://github.com/FAIRChemistry/MTPHandler/raw/refs/heads/main/docs/examples/data/spectra_max_190.txt" download>download</a>
the provided example data and the respective pre-filled out [plate map](https://github.com/FAIRChemistry/MTPHandler/raw/refs/heads/main/docs/examples/data/plate_map_SAHH_kinetics.xlsx).

### Install the `mtphandler` package
Copy the following code snippet into the first cell of your Jupyter Notebook and run it. This code snippet will install the `mtphandler` package if it is not already installed. This is a one-time setup and will not be required for future sessions.

```python
import sys
import subprocess
import shutil

# install git via conda if not installed
if not shutil.which("git"):
    print("Installing git via conda")
    subprocess.run(["conda", "install", "-y", "git"])
    if not shutil.which("git"):
        print("git is not installed")
        sys.exit(1)
print("git is installed")

# install mtphandler
try:
    from mtphandler import PlateManager

except ImportError:
    print("Installing mtphandler...")
    !pip install git+https://github.com/FAIRChemistry/MTPHandler.git --quiet

print("🏁 All set! Restart the Notebook once and you are ready to go.")
```

After you have run this code snippet, restart the Jupyter Notebook. You can do this by clicking on `Kernel` > `Restart Kernel...` in the top menu, or by clicking on the :material-reload: button in the top.

Verify that the installation was successful by running the following code snippet in a new cell:

```python
from mtphandler import PlateManager
```

If you do not get an error message, the installation was successful and the `PlateManager` is ready to use. Otherwise, please let us know.

## 🚀 Start using the `PlateManager`
Information on how to use the `PlateManager` can be found in the usage section of the [MTPHandler documentation](https://fairchemistry.github.io/MTPHandler/usage/).

__If you brougt your own data...__  
you can adjust the code snippets in the documentation to your needs and process your own data.

__If you do not have your own data...__
the provided data set is identical to the one used in the documentation. You can follow the steps in the documentation to process the provided data set.

## 🐞 If something doesn't work  
Please let us know and we will help you.

Alternatively, [use ChatGPT](https://chatgpt.com/) to ask for help. Therefore, copy and past the error message of the code cell into the chat and ask for help. The chatbot can mostly provide you with helpful. Furthermore, you can ask follow-up questions to get a better understanding of the problem.