---
title: Welcome to NetCon
description: Starting page for the NetCon documentatation
permalink: index.html
aliases:
  - LandingPage
draft: false
tags:
  - Index
date: 2024-09-26
Version: 2024.1.3
Product: NetCon 2.0
srcLang: en-US
---
This is the NetCon 2.0 [documentation](https://kenkor.github.io/NetCon/Home).
# It is all about the Network: NetCon

Welcome to the online Spatial Eye NetCon© Help site. 
Here you will find information about the why, what and how of reasoning about your network with NetCon.
Also, it provides information on how to install, configure and use NetCon, and its related components such as the [[./API/NetCon API Introduction|TraceAPI]] or Flow Calculation export.

Check out [[./Introduction/Copyright and Usage|Copyright and Usage]].

Currently this site is in English only.
## Introduction
This section provides a short [[./Introduction/Introduction|Introduction]] to the agnostic NetCon model for connectivity (also known as topology) for networks.

## Latest news
Around September 2024 there will be a pre-release to test out some new API's and the Net Congestion tooling.

## Version information

This section provides [[./Version And Release Information/Version Information#Releases|Version Information]], [[./Version And Release Information/Version Information#Release Notes|Release Notes]] and a [[./Version And Release Information/Road-map|Road-map]].

## Overview - Read me first

We recommend you take notice of the following introduction:
1. [[./Background information/Use Cases|Use Cases]]
2. [[./Overview/Purpose and Examples|Purpose and Examples]]
3. [[./Overview/Solution Architecture|Solution Architecture]]
4. [[./Overview/Sources of Connectivity|Sources of Connectivity]]
5. [[./Overview/Commodity Networks|Commodity Networks]]
6. [[./Overview/Network Ontology|Network Ontology]]
7. [[./Overview/Life Cycle Status|Life Cycle Status]]
8. [[./Overview/Barrier or Operational State|Barrier or Operational State]]
9. [[./Overview/Referential Information|Referential Information]]
10. [[./Overview/Network Sections|Network Sections]]

## Getting started

If you are new to NetCon, implement the basics by following the steps below

1. [[./Getting started/Download and Install NetCon|Download and Install NetCon]]
2. [[./Getting started/Connectivity Extraction Process|Connectivity Extraction Process]]
3. [[./Configuration/Viewing/Viewing Connectivity|Viewing Connectivity]]
4. [[Querying Connectivity|Querying Connectivity]]
## Configuration

Please follow the these steps

1. [[Configuring the Asset Registration for Extraction|Configuring the Asset Registration for Extraction]]
2. [[Clustering the Network into Sections|Clustering the Network into Sections]]
	1. [[Isolatable Sections|Isolatable Sections]]
	2. [[./Configuration/Warehouse/Operated Sections Model|Operated Sections Model]]
	3. [[Feeder or NetCongestion Sections|Feeder or NetCongestion Sections]]
	4. [[Custom Sections|Custom Sections]]
3. [[Configuring NetCon TraceAPI|Configuring NetCon TraceAPI]]
4. [[./Expressions/NetCon Expressions|Using NetCon Expressions]]
	1. [[Flow Calculation Export|Expressions for Flow Calculation exports]]
5. [[Materializing Long Running traces|Materializing Long Running traces]]

## User documentation

### NetCon data in Desktop Application or Web browser

* [[Viewing|Viewing]]
	* Styling of maps
	* Enriched data
	* Database relations
	* Asset relations
	* Expression relations
	* TraceDerivatives
	* Derived fields with [[./Expressions/NetCon Expressions|Using NetCon Expressions]] 

### NetCon API

* [[./API/NetCon API Calls|NetCon API Calls]]
* [[./API/Common parameters in the API|Common parameters in the API]]
* Search API
* Trace API
* Operate API
* Data Patch API
