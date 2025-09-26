# HL7MessageSplitAndSend
HL7 messages often contain multiple repeating segments such as NTE, AL1, OBX, ZTX, DG1, and others. These segments sometimes require individual processing and routing to different downstream systems. This technical paper introduces a configurable template designed to automate the splitting of these repeating HL7 segments, improving message handling and integration efficiency.
This template offers flexibility by allowing users to either send the message as-is with the required logic applied or split the message based on customizable settings defined within the business process configuration. Importantly, this approach supports reuse across various use cases and HL7 schemas.
Please note that you may need to update or modify a few lines of code depending on your HL7 schema or any custom schema you use. The source message must conform to your message schema.
Key configurable parameters include:
•	Message type selection
•	Identification of repeating segments
•	Segment group definitions
•	Unique identifier settings
Highlights:
•	The source message can contain multiple repeating segments such as NTE, AL1, OBX, etc.
•	You can send the entire message without splitting it, applying only your logic, to downstream systems.
•	Alternatively, you can split the message according to your instructions and send the segments separately to one or multiple downstream systems as needed.
This process is designed to split any repeating HL7 message segment and route it to the chosen downstream systems.  It functions as a reusable template, requiring little to no code modification to adapt to your specific needs.
The process provides dynamic configuration settings within the business process setup, allowing users to customize message splitting as needed. The main settings include:
SN	Setting Name	Short Description	Example
1.	MessageType  	HL7 message type used for splitting.	ADT^A01, ORU^01, DFT^P03 etc
2.	MultipleSegmentName	Repeating segment(s) in the HL7 message to be split individually. Specify the segment name that needs to be sent individually 	NTE, OBX, ZTX, RXP, etc.
3.	IsRepeating	Confirms if the segment in #2 repeats. Only "Y" is currently supported (default is "Y").	Y or N
4.	SegmentRepeatingGrp	Indicates if the segment is part of a group (e.g., RXCgrp()). Nested groups like PIDgrp().NTE() are not supported here.	RXCgrp(), PIDgrp(),

5.	MultipleSegGrpPath	
If #4 is "Y", define the path to the group. Can be selected from a list.
Note: You can edit or update this according to your requirements by changing the code.
Be careful, it depends on your message schema. If you have a custom schema, please update it accordingly.	PIDgrp() → NTE(), PIDgrp() → OBX() 
Select DropDownList: PIDgrp, MRGgrp, PRG1grp, IN1grp, ORCgrp(1).OBRuniongrp, PIDgrpgrp(1).ORCgrp(1).OBXgrp
6.	SegmentNameForUniqueID	Segment name to be used for generating a unique message identifier.	MHS or FT1grp
7.	SegmentDetails	Full segment path for inserting the value. Use the segment name if it's the same.	MSH, 
FT1grp(1).FT1
8.	SegmentFieldNo	Field number where the unique value should be inserted. Use the instance number.
	10 = (MSH:10 – Control id)
 2 = ( FT1grp(1).FT1.2 – Financial transaction id)
  
9.	SeperationUniqueID 	Separator for the unique value (e.g., ".", "#", "-"). Appends a unique number to the field value.	., #, -, etc
For example, such as XXXXX.1, XXXXX.2, etc.

Usage Instructions

1.	Copy the provided code and create a new business process in the HealthConnect Management Portal using the code class.
2.	Navigate to Process → Settings, then select TargetConfigurations.
 
3.	Choose the operations and target systems where you want to send the message.
4.	Configure all settings as specified in the table above according to your requirements and apply the changes.
5.	Restart your process to activate the new configuration.

