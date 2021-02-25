# factoryplus-cds-cnc
The Common Data Structure (CDS) for CNCs in JSON format.

The CDS is a common order and format of variables taken from different devices to ensure data/metadata is gathered in a consistent format when stored on the Factory+ network.

This initial draft was created from the CNC Companion Specification (https://opcfoundation.org/developer-tools/specifications-opc-ua-information-models/opc-unified-architecture-for-cnc-systems/) that has already been defined for OPC UA. This OPC UA data structure has been simplified for our use of MQTT/Sparkplug.

List of datatypes used for the variables in this CDS:

- String
- Boolean
- UInt8 and UInt32
- Double

These datatypes are what is currently being used. Any other Sparkplug compliant datatype can be used for "User_Defined" variables.

Example variable: an actual x position of the TCP in base coordinates would be located at "CncSystem/Titan1/CncChannelList/CncChannel1/PosTcpBcsX/ActPos".

## Future work
Can potentially upload a tag structure diagram to this repository to be able to better visualise the hierarchy. This would need to be kept upto date as the CDS structure is updated in future merges - may be worth doing programmatically in the future; automatically generate a diagram as edits are made to the JSON file?


## Notes/changes:

19/10/2020
- Simplified the OPC UA variable types so that the only datatypes found in the CDS are String, Boolean, UInt8, UInt32 and Double
- Whenever an array object is encountered, the subsequent level in the CDS path must be an additional level containing the object's index/name. This is denoted by variables within <> in the CDS and these should be changed to provide meaningful names. For example to obtain the actual position of a spindle, the CDS path would be "CncSpindleList/Spindle1/AnglePos/ActPos".
- Defined clear location called "User Defined/" where we can add tags that don't belong anywhere else in the CDS. This is a custom user-defined addition to the CDS.

11/01/2021

- updated `User_Defined` section to use Pascal_Snake_Case to be consistent with rest of Factory+ naming. The rest of the CDS uses PascalCase because that is what was used in the OPC UA Companion Specifications (only user defined variables need to use Pascal_Snake_Case).

25/01/2021

- removed `Metric Name` as the top level item
- put `User_Defined` as a folder under the `CncSystem/<CncName>/` folder structure. This is now consistent with all CDSs
