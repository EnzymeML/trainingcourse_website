# Project Status

The implementations of this project aim at simplifying the process of data acquisition and analysis and streamlining the process of making publication-ready datasets. In this regard the two tools `MTPHandler` and `ChromatoPy` are being developed, facilitating the handling of microplate data and chromatography data, respectively.

The conceptualized analysis workflow consists of the following steps, which are carried out in a Jupyter Notebook, where as the developed tools are used, depending on the experimental scenario.

## Implementation status [MTPHandler](https://github.com/FAIRChemistry/MTPHandler)
**Supported Systems**

- [x] SpectraMax M2
- [x] Magellan Sky 
- [ ] SpectraMax 190
- [ ] Tekan Spark
- [ ] BioTek Epoch

**Functionalities**

- [x] Read in data
- [x] Blanking of data
- [x] Creation of standard curves
- [x] Use of calibration curves for concentration calculation
- [x] Export of data to EnzymemML
- [x] Export of data to CSV
- [ ] Export of data to EnzymemML


## Implementation status [ChromatoPy](https://github.com/FAIRChemistry/chromatopy)
**Supported Systems**

- [x] Shimadzu LC-20
- [ ] Agilent ChemStation
- [ ] Water Acquity UPLC

**Functionalities**

- [x] Read in data
- [x] Peak detection/integration
- [x] Extract peaks of given retention time from many spectra
- [x] Concentration calculation via external standard
- [x] Export of data to CSV
- [ ] Export of data to EnzymemML
