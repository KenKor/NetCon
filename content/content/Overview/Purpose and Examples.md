---
title: Purpose and Examples
description: 
permalink: 
aliases:
  - single source of truth
  - data morphing
draft: false
date: 2024-09-27
tags:
  - single_source_of_truth
  - data_morphing
  - Overview
  - Index
  - ToDo
---
# Purpose and Examples

The *first* purpose of the NetCon model is to be the **single source of truth for network connectivity** - sometimes called network topology - to provide a vehicle for time-based working with any commodity network in a generic way, provisioning information exchanged with all consumers of the network connectivity data. As such, it provides a graph of atomic (indivisible) node/links.

It is very hard to get the data quality of a network connectivity to a high level, or even to a sufficient level. By being a single source of truth for many specific purposes at the same time, every effort to increase data quality for one consumer, will increase the data quality for all. Because no compromises can be made, we have developed standard techniques to store, reason with, validate, and report on the network.


> [!Important] First results
A remarkable result of this was, at the first implementation at the first customer, that the data quality in NetCon was overall 5% better (because it is using every source of connectivity) and also 2.5% worse (because NetCon will limit the 'as serviced' network to just assets that are in use, not those that are planned or out of service, which sounds obvious but is often not adhered to because of urgent reasons). That worse part is easily fixable by giving conducting assets the right asset life cycle status; obviously it is in service.

We have already seen much positive proof that a standard approach brings benefit and higher data quality to all consumers of NetCon. By being a standard model, many 'ready to go' applications can be developed that will be able to provide functionality for working with the network (see business cases). This is easily said, but not easily done, because the source data can be registered in quite different systems, in quite different ways. Therefore, NetCon is equipped with many options to morph or tailor the data to its consuming applications.

The following four examples illustrate this *second* purpose.
1. [[./Data Flow Example 1|Data Flow Example 1]] - Data flow example I: From GIS valve to simple flow calculation
2. [[./Data Flow Example 2|Data Flow Example 2]] - From ambiguous GIS valves information to flow calculation
3. [[./Data Flow Example 3|Data Flow Example 3]] - From GIS T-piece to simple flow calculation
4. [[./Data Flow Example 4|Data Flow Example 4]] - From GIS T-piece to Common Information Model
