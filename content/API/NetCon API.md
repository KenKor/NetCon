---
title: NetCon API
description: 
permalink: NetConApi
aliases: 
draft: false
date: 2024-09-30
tags:
  - Wildcard
  - ToDo
---
# NetCon API

The NetCon API a provides RESTfull to interact with NetCon data via the tracing engine. These services will use the engine in exactly the same way as [[NetCon|NetCon]].

The NetCon API [[./NetCon API Calls|calls]] can be split into four categories:

- (Meta) information, about the API and the server
- Look up and search, that will return connections,
- Trace and network following, that will return paths,
- Network manipulation, that will change the state and create data patches.  

Most parameters are optional. The combination of the parameters that you do (or do not) provide, will determine the result that you get.
  
### Wildcards
Some parameters can be supplied as an exact string value as well as a pattern supporting wildcards. The wildcard pattern works the same way as the Microsoft operating system supports file search: '?' must match one character, '\*' can match any character.
In addition, the comma ',' can be used to supply a list of values.

For example, this is denoted by the name of the parameter, e.g. [[./Parameters/AssetTableNameWildCard|AssetTableNameWildCard]] is the string or pattern that must match the `AssetTableName`.

Typically, the search with the exact value may be faster than the wildcard matching, but it is tried to evaluate the wildcards to possible values before starting the search.

In addition, an overall search parameter [[WildCardAsRegex|WildCardAsRegex]] parameter can be provided which will change the type of pattern matching that is done.
If this set to `true` than regex wildcards can be used instead of the '?', '\*' en ',' descrived above.

The default it simple wildcard matching, but you can override the default for all searches , as well as provide it as an argument for each search with the parameter `WildCardAsRegex`.

#ToDo

- Rename AssetTableNameWildCard to AssetTableNamePattern.
- In the expressions, it is called AssetTableName, but pattern matching still works.
 
To see and play with the services, the OpenAPI / SwaggerUI provided by the server can be used.

    https://servername.domain.local/swagger-ui/#/

    https://servername.domain.local/openapi

The NetCon API browser ui should look like this:

![[../Zimages/netcon_trace_api_in_browser.png|NetCon_Trace_API in browser]]

  
By clicking on one of the GET boxes above, you'll get the interaction screen:

![[../Zimages/netcon_trace_api_in_browser_trace_isolatable_section.png|NetCon_Trace_Isolatable Section API in browser]]
