# EnzymeML Suite

In order to install the EnzymeML Suite, choose one of the following options depending on your operating system:

- [Windows](https://github.com/JR-1991/enzymeml-dashboard/releases/download/v0.0.1/EnzymeML.Suite_0.0.1_x64-setup.exe)
- [Windows (MSI)](https://github.com/JR-1991/enzymeml-suite/releases/download/v0.0.1/EnzymeML.Suite_0.0.1_x64_en-US.msi)
- [macOS (Apple Silicon)](https://github.com/JR-1991/enzymeml-suite/releases/download/v0.0.1/EnzymeML.Suite_0.0.1_x64.dmg)
- [macOS (Intel)](https://github.com/JR-1991/enzymeml-dashboard/releases/download/v0.0.1/EnzymeML.Suite_0.0.1_x64.dmg)
- [Ubuntu](https://github.com/JR-1991/enzymeml-dashboard/releases/download/v0.0.1/enzyme-ml-suite_0.0.1_amd64.deb)

## Build the EnzymeML Suite from Source

If you experience any issues, you can build the EnzymeML Suite from source. Follow the steps below to set up and compile the project.

### Prerequisites

First, ensure your system is set up for Tauri. You can follow the instructions [here](https://tauri.app/v1/guides/getting-started/prerequisites) to install the required tools.

### Building the EnzymeML Suite

Once the prerequisites are installed, open a terminal and run the following commands:

```bash
# Clone the latest release of the EnzymeML Suite
git clone https://github.com/JR-1991/enzymeml-suite.git
git checkout tags/v0.0.1
cd enzymeml-suite

# Build the EnzymeML Suite
cargo tauri build --release
```

After the build completes, you should receive a message confirming the build was successful. The terminal will also display the path to the installer for the EnzymeML Suite.
