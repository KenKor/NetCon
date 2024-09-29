---
title: Barrier or Operational State
description: 
permalink: 
aliases: 
draft: false
date: 2024-09-27
tags:
  - Barrier
  - OperationalState
  - Overview
  - ToDo
---
# Barrier or Operational State

Connections can be conducting or barring/blocking the flow of the commodity.The flow is assumed to be barred when isbarrier > 0, and conducting/flowing isbarrier < 0. Normal connections that are not operated have isbarrier = 0.

Typical values are -1 (can be barrier) and 1 (is barrier). Other values are reserved 'mostly barring' behavior (2) for trickle throughput. Values > 9 and <-9 are reserved for autonomous switching behavior (< -9 when mostly conducting and > 9 for most barring).

#ToDo insert table.

