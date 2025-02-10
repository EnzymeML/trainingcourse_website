# Process Chromatographic Data

In this hackathon session, you will process your own chromatographic data using the `chromatopy` Python package. Alternatively, if you do not have your own data, or something fails, you can use the provided example data.

## 📚 Topics

1. You will get familiar with using Jupyter Notebooks and how you can run Python code locally on your computer.
2. You will learn how to process and enrich your chromatographic data using the `chromatopy` Python package.
3. You will yield a structured EnzymeML Document that can be used for further data analysis.

## 🛠️ Setup

### Start Jupyter Notebook
Start with opening Anaconda and launching a Jupyter Notebook. If this is the first time you ever used a Jupyter Notebook, you can find a short introduction [:simple-youtube: here](https://youtu.be/IMrxB8Mq5KU?si=UdcbsNZYd2S-Geg6&t=64). Otherwise, you can skip this step.

### Setup a project folder and notebook
Navigate to your desired location and create a new folder for your project. This folder will contain all the files you will create during this session.
Afterwards, create a new Jupyter Notebook in this folder. You can create new folders and the notebook directly from the Jupyter Notebook interface. Therefore, you can use the `New`:octicons-triangle-down-16: button in the top right corner and select `Folder` or `Notebook Python3 (ipykernel)`.

### Add the data to your project folder

__If you brought your own chromatographic data...__  
If you brought your own chromatographic file, add it to the project folder. Please make sure that your data is organized and processed in a way that it can be read by the `chromatopy` package. You can find the supported formats and data preparation in the [documentation of `chromatopy`](https://fairchemistry.github.io/chromatopy/supported_formats/).

__If you do not have your own data...__  
If you do not have your own data, you can [download](https://github.com/FAIRChemistry/chromatopy/raw/refs/heads/main/docs/examples/data/asm.zip) the example data set and add it to your project folder.

### Install the `chromatopy` package
Copy the following code snippet into the first cell of your Jupyter Notebook and run it. This code snippet will install the `chromatopy` package if it is not already installed. This is a one-time setup and will not be required for future sessions.

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

# install chromatopy
try:
    from chromatopy import ChromAnalyzer
except ImportError:
    print("Installing chromatopy...")
    !pip install git+https://github.com/FAIRChemistry/chromatopy.git
print("🏁 All set! Restart the Notebook once and you are ready to go.")
```

After you have run this code snippet, restart the Jupyter Notebook. You can do this by clicking on `Kernel` > `Restart Kernel...` in the top menu, or by clicking on the :material-reload: button in the top.

Verify that the installation was successful by running the following code snippet in a new cell:

```python
from chromatopy import ChromAnalyzer
```

If you do not get an error message, the installation was successful and the `ChromAnalyzer` is ready to use. Otherwise, please let us know.

## 🚀 Start using the `ChromAnalyzer`

The workflow for processing chromatographic data with the `ChromAnalyzer` is as follows:

If you use the example data, familiarize yourself with the [experimental scenario](https://fairchemistry.github.io/chromatopy/examples/peak_assignment/#kinetic-measurements)  
If you have calibration measurements for quantification, you should process these first.

1. Follow the instructions on how to find and integrate peaks with OpenChrom as outlined [here](https://fairchemistry.github.io/chromatopy/supported_formats/#spectrum-processing-with-openchrom-from-lablicate). If you already processed your data with OpenChrom, you can skip this step.

2. Read the chromatographic data files of one time-course series to create a `ChromAnalyzer` object. This can as outlined
[in the documentation](https://fairchemistry.github.io/chromatopy/examples/read_data/).

3. Visualize the chromatograms and the peak areas to check the quality of the data. This can be done as outlined
[in the documentation](https://fairchemistry.github.io/chromatopy/examples/visualize/). Are all peaks found? Are the peaks integrated correctly?

4. Assign the peaks to the respective compounds. This can be done as outlined [in the documentation](https://fairchemistry.github.io/chromatopy/examples/peak_assignment/#define-molecules).

5. If you plan to quantify the compounds, you find the instructions [here](https://fairchemistry.github.io/chromatopy/examples/peak_assignment/#calibration-measurements).

6. Lastly, you can export the data to an EnzymeML document. This can be done as outlined [in the documentation](https://fairchemistry.github.io/chromatopy/examples/peak_assignment/#convert-data).

## 🐞 If something doesn't work  
Please let us know and we will help you.

Alternatively, [use ChatGPT](https://chatgpt.com/) to ask for help. Therefore, copy and past the error message of the code cell into the chat and ask for help. The chatbot can mostly provide you with helpful. Furthermore, you can ask follow-up questions to get a better understanding of the problem.