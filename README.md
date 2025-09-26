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

![Table](https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Table.PNG)

## Usage Instructions
1.	Copy the provided code and create a new business process in the HealthConnect Management Portal using the code class.
2.	Navigate to Process → Settings, then select TargetConfigurations.
   ![Targe].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/TargetConfiguration.PNG)
4.	Choose the operations and target systems where you want to send the message.
5.	Configure all settings as specified in the table above according to your requirements and apply the changes.
6.	Restart your process to activate the new configuration.

## TESTING:
### Screenshot 1: Management Portal showing sending the entire source HL7 message and sending repeating segments to three different systems.
![ManagementPortal].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/ManagementPortal.PNG)

Select  Process  Setting and complete all the configuration according to your requirements.
### Screenshot 2.a: Process settings configuration screen.
![Screenshot 2a].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screenshot_2a.png)

If you need more information about any configuration, simply click the title for detailed explanations.

### Screenshot 2.b: Supporting information screen.
![Screenshot 2b].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screenshot_2b.png)

# Examples of Source and Target Messages: 
### Screenshot 3: Source message containing 5 repeating ZTX segments.
![Screenshot 3].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screenshot_3.png)

### Screenshot 4.a: Target system configuration sending the source message as-is and splitting the ZTX segments individually to operations.
![Screenshot 4a].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screenshot_41.png)

### Screenshot 4.b: Target system sending the source message as-is and splitting only the last ZTX segment to operations.
![Screenshot 4b].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screenshot_4b.png)

## Another example where only split messages are sent, without sending the original full message first:

### Screenshot 5: Source message with two ZTX segments split into two separate messages, each containing one ZTX segment.
### Screenshot 6: Source Message

![Screenshot 5_6].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_5_6.png)


### Screenshot 7.a: Target message containing the first ZTX  segment.
![Screenshot 7a].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_7a.png)

### Screenshot 7.b: Target message containing the second ZTX segment.
![Screenshot 7b].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_7b.png)

## Additional Example with Different Configurations
In this example, the source message contains multiple repeating NTE segments, where each NTE segment is part of the group path: PIDgrpgrp().ORCgrp().OBXgrp.
The process is configured to split and send each NTE segment individually to the target system. The resulting target messages are shown below:

•	Screenshot 10.a – First NTE segment

•	Screenshot 10.b – Second NTE segment

•	Screenshot 10.c– Third NTE segment


### Screenshot 8: Process Configurations
![Screenshot 8].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_8.png)

### Screenshot 9: Source message 
![Screenshot 9].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_9.png)

### Screenshot 10.a: Target message – First NTE segment
![Screenshot 10a].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_10a.png)
### Screenshot 10.b: Target message – Second NTE segment
![Screenshot 10b].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_10b.png)
### Screenshot 10.c: Target message – Third NTE segment
![Screenshot 10c].(https://raw.githubusercontent.com/pandeySR/HL7MessageSplitAndSend/main/Images/Screensthot_10c.png)

I hope this template will help streamline your HL7 message processing. If you have any questions or need further assistance, please feel free to ask.
Thank you.

Thank you.
