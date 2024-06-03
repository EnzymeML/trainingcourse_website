Using `MTPHandler`, plate data from various instruments can be read and processed. The goal of the processing is to enrich the information associated with each well of the plate and process the measured signal. This includes the assignment of chemical species alongside their initial concentrations within the well.

## Assignment of species to wells

After the data is loaded to the `Plate` object of the `MTPHandler`, different chemical species can be assigned to different `Well` objects, each with a different initial concentration. This crucial definition step builds the foundation of all subsequent analysis steps since the measurement conditions are connected to the measured data.
Instead of defining the initial conditions for each well separately, `MTPHandler` allows assignment of initial conditions species-wise. In this process, the initial conditions of a species can be assigned for an individual row/column or to all wells at once.
Assignment of initial conditions using a plate map

If the concentration of a species is different in all wells of a plate, the initial conditions for that species can be mapped to the data using a plate map, which can be defined as a separate sheet in an Excel file. The plate map needs to have an index row labeled with the column numbers 1-12 as well as an index column labeled with the row indices A-H. The values in the plate map are then assigned as the initial concentrations of that species.

## Processing of measured signal

The assigned initial conditions are also utilized for automated blanking of the plate. Consider the following example: A plate is prepared in which all wells contain buffer. All wells except for A1, A2, and A3 contain a catalyst and all wells except for A1, A2, A3, B1, B2, and B3 contain substrate for the catalyst.
If now the contribution of the buffer signal should be subtracted from the measured data, the blanking routine looks out for wells that only contain the buffer species. Thus, it finds wells A1, A2, and A3. Therefore, the mean signal value is calculated and subtracted from all wells, which contain the buffer species with the same concentration. If now the contribution of the catalyst should be subtracted from the signal, the blanking function finds wells B1, B2, and B3 and repeats the blanking process. Finally, all measured data is blanked and the measured signal can be solely attributed to the substrate.

## Differentiation between wells with and without catalyst

Furthermore, the assignment of initial conditions allows a decision on the purpose of each well in the context of the experiment. For instance, a standard for the measured substrate might be prepared on the same plate as wells with proceeding reactions. Due to the previous assignment, wells without the catalyst species can be extracted and forwarded to the method creating a standard curve for concentration calculation out of these wells. The remaining wells can then be used to transform the measured signal into concentration data. Subsequently, the data can be transformed into an EnzymeML Document allowing further analysis of the data.

!!! Example
    Try the [`plate example`](https://github.com/EnzymeML/trainingcourse_website/tree/main/notebooks/plate) by downloading the Notebook file and the measurement file. Open the Jupyter Notebook in the Jupyter Lab container and read the measurement file. 

!!! Info "Currently under construction 🚧"
    Creation of a standard curve and EnzymeML Document are not available in the current version.
