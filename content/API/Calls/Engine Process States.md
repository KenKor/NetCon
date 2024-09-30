---
title: states
description: 
permalink: Calls/Engine-States
aliases: 
draft: false
date: 2024-09-30
tags:
  - States
  - ApiMetaCall
  - ApiCall
  - ToDo
---
# API Meta States

The Search Call `states` retrieves the all state information of initialisation and other tasks performed by the trace engine.

In this information, one can see if the initialisation has been completed, how long it took, the size of the networks, and possible failures.

#ToDo At this moment the services are only available after full initialisation for safety when running Warehouse batches. This may change in the future. As long as that is the case, the parameters below are irrelevant._

## Parameters
| Link                                                                                  | type    | mand  | description                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------- | ------- | ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[../Parameters/Progress State/WaitTillInitialized\|WaitTillInitialized]] | boolean | false | Optional parameter, the default value is 'false'. If 'true', the call will wait for the initialization to complete before returning.                                                         |
| [[../Parameters/Progress State/WaitMilliSeconds\|WaitMilliSeconds]]       | integer | false | Optional parameter, the default value is '-1'. If  the `WaitTillInitialized` is set, this second parameter will specify the maximum of miliseconds that the call will wait before returning. |


## Results
| Link                                                                 | type     | unique | description                                                                                                                                                                                                                               |
| -------------------------------------------------------------------- | -------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[../Results/Progress State/ProcessName\|ProcessName]]   | string   | true   | Name identifying the subprocess or task that has been started and for which a state is being logged and monitored.                                                                                                                        |
| [[../Results/Progress State/ProcessState\|ProcessState]] | string   | false  | State of the process, which is 'initialisation' when it is a start up process, 'executing' when it is a normal process, 'finished' when the task or the subprocesses have completed, and 'failed' if the process has raised an exception. |
| [[../Results/Progress State/StartTime\|StartTime]]       | datetime | false  | The moment that the process was started.                                                                                                                                                                                                  |
| [[../Results/Progress State/Duration\|Duration]]         | timespan | false  | Specifices the time it took to perform `Name`. Only available when completed.                                                                                                                                                             |
| [[../Results/Progress State/Message\|Message]]           | string   | false  | Last message provided as logging information for this state.                                                                                                                                                                              |
| [[../Results/Progress State/PeakMemory\|PeakMemory]]     | long     | false  | The peak memory that the server is consuming measured during the execution of this process,                                                                                                                                               |




Example query to retrieve the state information: 

    https://server.domain.local/api/v2/netcon/v1/states

Example query to retrieve the state information and wait maximum 60 seconds for initialisation:

    https://server.domain.local/api/v2/netcon/v1/states?WaitTillInitialized=true&WaitMilliSeconds=60000