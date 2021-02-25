# Factory+ CNC Common Data Structure

The CDS is a common order and format of variables taken from different devices to ensure data/metadata is gathered in a consistent format when stored and shared across the the Factory+ architecture.

This initial draft was created from the [CNC Companion Specification](https://opcfoundation.org/developer-tools/specifications-opc-ua-information-models/opc-unified-architecture-for-cnc-systems/) that has already been defined for OPC UA. This OPC UA data structure has been simplified for our use of MQTT/Sparkplug.

List of datatypes used for the variables in this CDS:
- String
- Boolean
- UInt8 and UInt32
- Double

These datatypes are what is currently being used. Any other Sparkplug compliant datatype can be used for `User_Defined` variables.

Example variable: an actual `x` position of the TCP in base coordinates would be located at `CncSystem/Titan1/CncChannelList/CncChannel1/PosTcpBcsX/ActPos`.
