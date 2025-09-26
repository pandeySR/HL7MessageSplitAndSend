# A Configurable Template for Automated Splitting of HL7 Repeating Segments

## Introduction
HL7 messages often contain multiple repeating segments such as NTE, AL1, OBX, ZTX, DG1, and others. These segments sometimes require individual processing and routing to different downstream systems. This technical paper introduces a configurable template designed to automate the splitting of these repeating HL7 segments, improving message handling and integration efficiency.
This template offers flexibility by allowing users to either send the message as-is with the required logic applied or split the message based on customizable settings defined within the business process configuration. Importantly, this approach supports reuse across various use cases and HL7 schemas. Please note that you may need to update or modify a few lines of code depending on your HL7 schema or any custom schema you use. The source message must conform to your message schema.

## Key configurable parameters include:

•	Message type selection

•	Identification of repeating segments

•	Segment group definitions

•	Unique identifier settings


## Highlights:

•	The source message can contain multiple repeating segments such as NTE, AL1, OBX, etc.

•	You can send the entire message without splitting it, applying only your logic, to downstream systems.

•	Alternatively, you can split the message according to your instructions and send the segments separately to one or multiple downstream systems as needed.

This process is designed to split any repeating HL7 message segment and route it to the chosen downstream systems.  It functions as a reusable template, requiring little to no code modification to adapt to your specific needs. The process provides dynamic configuration settings within the business process setup, allowing users to customize message splitting as needed. The main settings are detailed in Table 1 below:

The process provides dynamic configuration settings within the business process setup, allowing users to customize message splitting as needed. The main settings are detailed in Table 1 below:

### Table 1: Process Settings – Configurations
![Images](https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Table.png)

![Images](Table.png)

## Usage Instructions
1.	Copy the provided code and create a new business process in the HealthConnect Management Portal using the code class.
2.	Navigate to Process → Settings, then select TargetConfigurations. 
3.	Choose the operations and target systems where you want to send the message.
4.	Configure all settings as specified in the table above according to your requirements and apply the changes.
5.	Restart your process to activate the new configuration.

For detailed configuration, please log in to the InterSystems Community and view the guideline document, which demonstrates all the steps with screenshots.

Thank you.
