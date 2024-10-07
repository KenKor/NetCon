---
title: Atomic Model configuration
description: 
permalink: 
aliases: 
draft: false
date: 2024-10-02
tags: 
---
# Atomic Model configuration


### Atomic Model configuration

The atomic model is not intended for customization. In due time the seProject will be replaced by software, so changes that you will do make will forfeit in the future.

These items need to be configured:

- Name of the target warehouse model. For this, open the 'target' feature source, create the logical target model with the right coordinate system (same as other logical warehouse models that are used for assets), and set it as a target.
- Names of the input tables:
  - Rewire these by using the change feature source table function to the output of the NetConBase Output objects. E.g. the netcon_basenode table is called e_netcon_basenode, g_netcon_basenode, eo_netcon_basenode or gdo_netcon_basenode, hence the business collections are adapted.
- Name of the output table:
  - E.g. the netcon_connection table is adapted to the output, analogue to the input tables used. E.g. e_netcon_connection, g_netcon_connection, eo_netcon_connection or gdo_netcon_connection respectively.

#### NetCon Connection

The NetCon Connection table represents a network graph. One table can exist per discipline, e.g. electricity, gas, water or telecom. If a network is connected, it should be in a single NetCon Connection table, e.g. gas high pressure and low pressure (connected by a regulating station), or industry and household water (connected by a filtering plant), telecom fibre, coax and ethernet (connected by signal converters) should each be in a single table for their discipline.

(Note that this is different from Smallworld manifold.)

The definition of the table contents is standard and should not be altered.

Field          | Name | Description
------------   | ---- | -----------
se_history_id* | Meta History Id | Spatial Warehouse Key, see [User data - Spatial Warehouse User Guide (spatial-eye.com)](https://documentation.spatial-eye.com/swh/2021_2/en/143117a0-d822-42f1-ae69-a484a2db0efa.htm).
se_history_rootid* | Meta History Root Id | Spatial Warehouse Group Key per source record.
fromid*            | From Id | Node Id where connection starts from.
toid*              | To Id | Node Id where connection goes to.
role               | Role | Enumerator denoting rol of connection in network. See also [Role](Atomic%2520Model%2520configuration.md##netcon-role).
bidrectional       | Bidirectional | 0 if just going from fromid to toid, 1 if this connection also represents the reverse going from toid to fromid.
isbarrier          | Is Barrier | Enumerator. 0 if not a barrier, 1 if barring and connection is 'off', -1 if it can be barring but connection is 'on', i.e. conducting. Other values reserved for the future.
edgetype           | Edge Type | Enumerator. 0 = node, 1 = link, 2 = terminal. See also [Edge Type](Atomic%2520Model%2520configuration.md##netcon-edge-type).
cost               | Cost | Double precision indicating cost, impedance or resistance.
commodity          | Commodity | The stuff being transported, e.g. HV, MV, LV for high voltage, and `abc` or '123' for the phases, or ‘u’ (1 unknown phase), combined, e.g. 'LV:abc'. Similarly, this could be HP or LP (high or low pressure) followed by the type of gas CH4 or H2, etc.
statuscode         | Status Code | Enumerator indicating the status life cycle time dimension. See also [Status](Atomic%2520Model%2520configuration.md##netcon-status).
geometryl          | Geometry Line | Multiple Line geometry (for links and hyperlinks).
geometryp          | Geometry Point | Multiple Point geometry (for points and long hyperlinks).
assettablename     | Asset Table Name | Name of the table representing the assets in the registration system as it is ETL-ed into Spatial Warehouse. Hence, if the name is translated or corrected for typo's in the warehouse repository, the same name should be used here.
assetid            | Asset Id | Positive long value denoting the Id of the original record this data came from in the source system. Note that for various reason this Id is by far not unique in the connection table.
specification      | Specification | Pointing to an entry in the specification table for asset table name.
assethierarchy     | Asset Hiearchy | Information about containers and related data to the connection. E.g. 'substation.id=123' or 'ean.id=456,ean.id=457' to denote a connection is in a particular substation or is connected to two smart meters with ean id.
customassetid      | Custom Asset Id | String key relating to an enterprise wide reference present in the registration system.
owner              | Owner | String value denoting if this connection has a deviating owner, <null> otherwise.
operatedby         | Operated By | String value denoting if this connection is not operated by default party, but by a deviating party, <null> otherwise.
manifoldcode       | Manifold Code | May be dropped in the future. Enumerator referring back to the source system, see [Manifold](Atomic%2520Model%2520configuration.md##manifold-definition).
rwocode            | RWO Code | May be dropped in the future. Enumerator referring back to the source system, see [Real-world Object](Atomic%2520Model%2520configuration.md##rwo-definition).
geomappcode        | Geom App Code | May be dropped in the future. Enumerator referring back to the source system, see [Geom App Code](Atomic%2520Model%2520configuration.md##geom-attribute-definition).

