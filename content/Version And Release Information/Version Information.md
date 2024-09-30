---
title: Version Information
description: 
permalink: 
aliases: 
draft: false
date: 2024-09-27
Version: 2024.1.3
Product: NetCon 2.0
---
# Releases

| Version  | Released |
| :------: | -------- |
| 2022.4.0 | dec 2022 |
| 2023.1.1 | mar 2023 |
| 2023.3.1 | nov 2023 |
| 2023.3.3 | mar 2024 |
| 2024.1.2 | okt 2024 |

This section contains the version information for the `Spatial Eye NetCon` product(s). The product's change history is described below for each of the released versions.

- [[Version Information#Spatial Eye NetCon 2023.3.3|Spatial Eye NetCon 2023.3.3]]
- [[Version Information#Spatial Eye NetCon 2023.4.1|Spatial Eye NetCon 2023.4.1]]

---
# Release Notes
## Spatial Eye NetCon 2023.3.3

New:
- [[../Expressions/NetCon Expressions|NetCon Expressions]] to compute traces and query in all the Spatial Eye products.
- [[NetCon TraceApi|NetCon TraceApi]] has been made available for the Spatial Eye server product.
- [[../API/Results/Connection Or Path Results/Label|Label]] property has been added to the Connection definition to allow for a company wide name ontology.
- [[../API/Parameters/SpecificationPattern|SpecificationPattern]] property has been added to enable a central specification system to enrich assets with type or manufacturer specification information.

Updated:
* The network cluster-er is extended with the ability to compute different cluster sections in one batch.

---
## Spatial Eye NetCon 2023.4.1

New:
- [[Flow calculation|Flow calculation]] is added and computed on the fly to determine the direction of the flow (none, down or mazed) for every connection.
- [[Flow calculation export|Flow calculation export]] is enabled for various network flow calculation programs.
- [[NetCon sections|NetCon sections]] are computed on the fly. This allows for a faster startup. Sections are name Isolatable, Operated, Feeder and Custom sections. The sections have now more attributes than the previous Section and Super sections. The relations between sections and connections have been simplified.
- [[Specification enrichment|Specification enrichment]], [[Asset Hierarchy enrichment|Asset Hierarchy enrichment]] and [[Asset enrichment|Asset enrichment]] have been added to enable central enrichment of connectivity information. This way, the entire organisation can benefit from a single source of truth.
- [[NetCon TraceApi|NetCon TraceApi]] has been made available for the Spatial Eye server product.
- Over 300 units tests have been programmed that are run as part of the release process.

Updated:
* The tracing algorithms have been rewritten to inherit from the same abstract class. They are all operating in a streamed fashion.
- [[../Expressions/NetCon Expressions|NetCon Expressions]] have been added and rewritten.
- [[NetCon TraceApi|NetCon TraceApi]] has been made streamed where possible. Because of this the output objects has a different field order.
