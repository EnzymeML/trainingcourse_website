Using `MTPHandler`, plate data in from various instruments can be read and processed. Goal of the processing is to enrich the information associated with each well of the plate and process the measured signal. This includes the assignment of chemical species aslongside their initial concentrations within the well. Forthermore,

## Assignment of species to wells

After the data is loaded to the `Plate` object of the `MTPHandler`, different chemical species can be assigned to different `Well` object, each with an different initial concentration. This crucial definitial step builds the foundation of all subsequent analysis steps, since the measurement conditions are connected to the measured data.
Insted of defining the inital condtions for each well speperatly, `MTPHandler` allows to assign the initial conditions species-wise. In this process the initial conditions of a species can be assign for an individual row / column or to all wells at once.

## Assignment initial conditions using a plate map

If the concentration of a species is different in all wells of a plate, the initial conditions for that species can be mapped to the data using a plate map, which can be dafined as a seperate sheet in an excel file. The plate map needs to have an index row labeled with the column numbers from 1-12 as well as an index column labeled with the row indicex A-H. The values in the plate map are then assigned as the initial concentrations of that species.

## Processing of measured signal

The assigned initial conditions are also utilized for automated blanking of the plate. Consider the following example: A plate is prepared in which all wells contain buffer. All well except for A1, A2, and A3 contain a catalyst and all wells except for A1, A2, A3, B1, B2, and B3 contain substrate for the catalyst.
If now the contribution of the buffer signal should be subtracted from the measured data, the blanking routine looks out for wells which only contain the buffer species. Thus, it findes wells A1, A2, and A3. Thereof, the mean signal value is calculated and subtracted from all wells, which contain the buffer species with the same concentration. If now the contibution of the catalyst should be subtracted from the signal, the blanking funktion finds wells B1, B2, B3 and repeats the blanking process. Finally, all measured data is blanked and the measured signal can be solely attributed to the substrate.

## Differentiation between wells with and without catalyst

Furthermore the asignment of initial condition allows to automatically decide on the purpose of each individual well in the context of the experiment. For instance a standard for the measured substrate might be prepared on the same plate as wells with proceeding reactions. Due to the previous assignment, wells without the catalyst species can be extracted and forwarded to the method creating a standard curve for concentration calculation out of these wells. The remaining wells can then be used to transform the measured signal to concentration data. Subsequently, the data can be rtansformed into an EnzymeML Document allowing further analysis of the data.

!!! Info "Currently under cunstruction 🚧"
    Creation of a standard curve and EnzymeML Document are not available in the current version.


!!! Example
    Try the EXAMPLENOTEBOOK. Try to read in and assign initial conditions for your photometer
