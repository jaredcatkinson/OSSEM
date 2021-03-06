---
title: Event ID 5 - Process terminated
description: The process terminate event reports when a process terminates.
log.type: sysmon
sysmon.version: 7.01
sysmon.rule: ProcessTerminate
author: Roberto Rodriguez (@Cyb3rWard0g)
date: 04/11/2018
---

# Event ID 5: Process terminated

## Description
The process terminate event reports when a process terminates. It provides the UtcTime, ProcessGuid and ProcessId of the process.[Sysmon Source](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon#event-id-5-process-terminated)

## Event Log Illustration

<img src="https://github.com/Cyb3rWard0g/OSSEM/blob/master/resources/images/event-5.png" alt="Event 5 illustration" width="625" height="625">

## Event XML:

```
<Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
  <System>
    <Provider Name="Microsoft-Windows-Sysmon" Guid="{5770385F-C22A-43E0-BF4C-06F5698FFBD9}" /> 
    <EventID>5</EventID> 
    <Version>3</Version> 
    <Level>4</Level> 
    <Task>5</Task> 
    <Opcode>0</Opcode> 
    <Keywords>0x8000000000000000</Keywords> 
    <TimeCreated SystemTime="2018-04-11T05:37:43.157314700Z" /> 
    <EventRecordID>11753935</EventRecordID> 
    <Correlation /> 
    <Execution ProcessID="6028" ThreadID="4132" /> 
    <Channel>Microsoft-Windows-Sysmon/Operational</Channel> 
    <Computer>DESKTOP-WARDOG</Computer> 
    <Security UserID="S-1-5-18" /> 
  </System>
  <EventData>
    <Data Name="UtcTime">2018-04-11 05:37:43.153</Data> 
    <Data Name="ProcessGuid">{A98268C1-9ECD-5ACD-0000-0010EF6BAF00}</Data> 
    <Data Name="ProcessId">2428</Data> 
    <Data Name="Image">C:\Windows\System32\backgroundTaskHost.exe</Data> 
  </EventData>
</Event>
```

## Data Dictionary

|	Standard Name	| Field Name |	Type	|	Description	|	Sample Value	|
|	----------------	|	----------------	|	----------------	|	----------------	|	----------------	|
|	event_creation_time	|	UtcTime	|	date	|	Time in UTC when event was created	|	4/11/18 5:37	|
|	process_guid	|	ProcessGuid	|	string	|	Process Guid of the process that terminated	|	{A98268C1-9ECD-5ACD-0000-0010EF6BAF00}	|
|	process_id	|	ProcessId	|	integer	|	Process ID used by the os to identify the process that terminated	|	2428	|
| process_name | Image | string | The name of the executable of the process that terminated | backgroundTaskHost.exe |
| process_path | Image | string | File path of the process that terminated | C:\Windows\System32\backgroundTaskHost.exe |