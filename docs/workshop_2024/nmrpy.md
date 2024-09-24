# Process NMR Data

In this hackathon session, you will process your own time-course data from NMR using the `NMRpy` Python package. Alternatively, if you do not have your own data, or something fails, you can use the provided example data.

## 📚 Topics

1. You will get familiar with using Jupyter Notebooks and how you can run Python code locally on your computer.
2. You will learn how to process and enrich your NMR data using the `NMRpy` Python package.
3. You will yield a structured EnzymeML Document that can be used for further data analysis.

## 🛠️ Setup

### Start Jupyter Notebook

Start with opening Anaconda and launching a Jupyter Notebook. If this is the first time you ever used a Jupyter Notebook, you can find a short introduction [:simple-youtube: here](https://youtu.be/IMrxB8Mq5KU?si=UdcbsNZYd2S-Geg6&t=64). Otherwise, you can skip this step.

### Setup a project folder and notebook

Navigate to your desired location and create a new folder for your project. This folder will contain all the files you will create during this session.
Afterwards, create a new Jupyter Notebook in this folder. You can create new folders and the notebook directly from the Jupyter Notebook interface. Therefore, you can use the `New`:octicons-triangle-down-16: button in the top right corner and select `Folder` or `Notebook Python3 (ipykernel)`.

### Add the data to your project folder

__If you brought your own NMR data...__  
If you brought your own chromatographic file, add it to the project folder. Please make sure that your data is organized in a way that it can be read by the `NMRpy` package. You can find the supported formats  in the [documentation of `NMRpy`](https://nmrpy.readthedocs.io/en/latest/).

__If you do not have your own data...__  
If you do not have your own data, you can use the example data set found in the `NMRpy_tutorial` [repository on GitHub](https://github.com/FAIRChemistry/nmrpy_tutorial/tree/main) in the `tutorial/data/` directory.

### Install the `NMRpy` package

Copy the following code snippet into the first cell of your Jupyter Notebook and run it. You will also find this code snippet in the Notebooks found in the [tutorial repository on GitHub](https://github.com/FAIRChemistry/nmrpy_tutorial/tree/main). This code snippet will install the `NMRpy` package and additional dependencies like `pyenzyme` if they are not already installed. This is a one-time setup and will not be required for future sessions.

```python
import sys
import subprocess
import shutil
import importlib

def install_and_import(package):
    try:
        importlib.import_module(package)
        print(f"{package} is already installed")
    except ImportError:
        print(f"Installing {package}")
        %pip install {package}

# install git via conda if not installed
if not shutil.which("git"):
    print("Installing git via conda")
    subprocess.run(["conda", "install", "-y", "git"])
    if not shutil.which("git"):
        print("git is not installed")
        sys.exit(1)
print("git is installed")

# install NMRpy and other packages
try:
    import nmrpy
    rint("NMRpy is already installed")
except ImportError:
    print("Installing NMRpy...")
    %pip install git+https://github.com/NMRPy/nmrpy@adapt-to-pydantic-v2 --quiet

install_and_import("matplotlib")
install_and_import("ipyfilechooser")
install_and_import("rich")
install_and_import("pyenzyme")

print("🏁 All set! Restart the Notebook once and you are ready to go.")
```

After you have run this code snippet, restart the Jupyter Notebook. You can do this by clicking on `Kernel` > `Restart Kernel...` in the top menu, or by clicking on the :material-reload: button in the top.

Verify that the installation was successful by running the following code snippet in a new cell:

```python
import nmrpy
```

If you do not get an error message, the installation was successful and `NMRpy` is ready to use. Otherwise, please let us know.

## 🚀 Start using the `NMRpy`

The workflow for processing chromatographic data with `NMRpy` is as follows:

1. If you use your own data, you will have to prepare an EnzymeML document containing the relevant experiment metadata as showcased in the [tutorial notebook](https://github.com/FAIRChemistry/nmrpy_tutorial/blob/main/tutorial/create_enzymeml4nmrpy_v2.ipynb). You will need information on species measured, the reaction(s), and the measurement.

2. Follow the instructions on how to load an NMR dataset as outlined in the [official documentation](https://nmrpy.readthedocs.io/en/latest/) and in the [tutorial notebook](https://github.com/FAIRChemistry/nmrpy_tutorial/blob/main/tutorial/enzymeml_workshop.ipynb).

3. Pre-process the data, if necessary, as required by the dataset.

4. Analyze the data to arrive at the desired concentration data and apply it to the EnzymeML document.

## 🐞 If something doesn't work

Please let us know and we will help you.

Alternatively, [use ChatGPT](https://chatgpt.com/) to ask for help. To do so, copy and past the error message of the code cell into the chat and ask for help. The chatbot can mostly provide you with helpful. Furthermore, you can ask follow-up questions to get a better understanding of the problem.
