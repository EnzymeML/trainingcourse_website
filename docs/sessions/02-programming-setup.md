# Programming Setup

## Required Software

### 1. Cursor IDE
Cursor is an AI-powered code editor that can help you write code faster and more efficiently. For more information and to install it, please visit the [Cursor website](https://www.cursor.com/).

### 2. Python Environment
We'll use Conda as our Python environment manager. It's available for Windows, macOS, and Linux.

## Installing Conda

Choose one of these distributions:
- **Miniconda**: Lightweight version
- **Anaconda**: Full package suite
- **Miniforge**: Community-driven version

### Windows Installation
1. Download the installer from your chosen distribution
2. Run the `.exe` file and follow the installation wizard
3. Verify installation by opening Anaconda/Miniforge Prompt:
   ```bash
   conda list
   ```

### macOS Installation
1. Download your chosen installer
2. Open terminal and run:
   ```bash
   bash <conda-installer-name>-latest-MacOSX-x86_64.sh
   ```
3. Close and reopen terminal
4. Verify installation:
   ```bash
   conda list
   ```

### Linux Installation
1. Download Miniconda:
   ```bash
   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
   ```
2. Install:
   ```bash
   bash Miniconda3-latest-Linux-x86_64.sh
   ```
3. Restart terminal
4. Verify installation:
   ```bash
   conda list
   ```

## Working with Conda Environments

### Creating Environments
Create a new environment with specific Python version and packages:
```bash
conda create -n my_project_env python=3.10 numpy pandas
```

### Managing Environments
- **Activate** an environment:
  ```bash
  conda activate my_project_env
  ```
- **List** all environments:
  ```bash
  conda env list
  # or
  conda info --envs
  ```
- **Install** packages in active environment via `pip`:
  ```bash
  pip install scipy matplotlib
  ```

## IDE Setup

### Setting Up Conda in Cursor/VSCode

1. Activate your environment:
   ```bash
   conda activate my_project_env
   ```

2. Install Jupyter kernel:
   ```bash
   conda install ipykernel
   ```

3. Configure VSCode:
   - Install Python extension from marketplace
   - Press `Ctrl + Shift + P` (or `Cmd + Shift + P` on macOS)
   - Search for "Select Python Interpreter"
   - Choose your Conda environment
