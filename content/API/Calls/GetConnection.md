---
title: get-connection
description: 
permalink: Calls/GetConnection
aliases: 
draft: false
date: 2024-09-27
tags:
  - GetConnection
  - ApiSearchCall
  - ApiCall
  - ToDo
---
# API Search GetConnection

The Search Call `get-connection` retrieves all connectivity information for an asset.
For a point object, it will retrieve one record, unless terminals are generated, in which case those are retrieved as well.
For a line object, one or many records can be retrieved depending on whether the object is split in the underlying topology model of the registration system.

If the search parameters are specified as wildcards, many matching records can be retrieved.

If no parameters are provided, the [[Sources|Sources]] (see also [[Role|Role]]) in the network are retrieved.

## Parameters
| Link                                                                         | type   | mand  | description                                                                                                                                                                                                                                           |
| ---------------------------------------------------------------------------- | ------ | ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[../Parameters/AssetTableNameWildCard\|AssetTableNameWildCard]] | string | false | Name of the asset table in the NetConConnection table. It may contain wild cards if you want to search more than one table. If this parameter is kept empty (no name and no pattern), it will change the interpretation of the [[AssetId|AssetId]] parameter. |
| [[../Parameters/AssetId\|AssetId]]                               | long   | false | The number that matches the AssetId of one or more of the NetConConnections exactly. If AssetTableNameWildCard is empty this parameter will be interpreted as ConnectionId.                                                                           |
| [[../Parameters/CustomAssetId\|CustomAssetId]]                   | string | false | The string that matches the CustomAssetId of one or more of the NetConConnections exactly.                                                                                                                                                            |
| [[../Parameters/LabelWildCard\|LabelWildCard]]                   | string | false | The string or pattern that matches the Label of the NetConConnection, if this was provided. For example: "circuitbreaker:1234" or "circuitbreaker*" or "123456789-*".                                                                                 |


## Results
| Link                                                  | type    | unique | description                                                                   |
| ----------------------------------------------------- | ------- | ------ | ----------------------------------------------------------------------------- |
| [[../Results/StartCount\|StartCount]]     | int     | false  | Number of connections that have been retrieved by using the start parameters. |
| [[../Results/ResultsCount\|ResultsCount]] | int     | false  | Number of connections that have been retrieved by performing the search.      |
| [[../Results/Success\|Success]]           | boolean | false  | True if any results have been retrieved.                                      |


## Connections
| Link                                                                               | type    | unique | description                                                                           |
| ---------------------------------------------------------------------------------- | ------- | ------ | ------------------------------------------------------------------------------------- |
| [[../Results/Connection Or Path Results/Id\|Id]]                       | long    | true   | Id for the NetCon connection as described in this document.                           |
| [[../Results/Connection Or Path Results/FromId\|FromId]]               | long    | false  | Id identifying the node departing from.                                               |
| [[../Results/Connection Or Path Results/ToId\|ToId]]                   | long    | false  | Id identifying the node going to.                                                     |
| [[../Results/Connection Or Path Results/BiDirectional\|BiDirectional]] | boolean | false  | False if this connection goes only from FromId to ToId, true if it also returns back. |


---
Example query to find Asset with TableName = 'e_lv_house_connection' and Id = 123:

    https://server.domain.local/api/v2/netcon/v1/get-connection?AssetTableNameWildCard=e_lv_house_connection&AssetId=123

Example query to find Asset with TableName = 'e_lv_house_connection' and CustomAssetId = 'EAN_978132897312879':

    https://server.domain.local/api/v2/netcon/v1/get-connection?AssetTableNameWildCard=e_lv_house_connection&CustomAssetId=EAN_978132897312879

Example query to find Asset with TableName = 'unknown' and Id = 123:

    https://server.domain.local/api/v2/netcon/v1/get-connection?AssetTableNameWildCard=*&AssetId=123

Example query to find Asset ConnectId = 987:

    https://server.domain.local/api/v2/netcon/v1/get-connection?AssetId=987

#ToDo Add example outcome.
