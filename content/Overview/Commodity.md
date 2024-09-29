---
title: Commodity
description: 
permalink: 
aliases: 
draft: true
date: 2024-09-27
tags:
  - Commodity
  - Overview
  - ToDo
---
---
# Commodity

The commodity of a network is what is being transported by it.
The items in the commodity are abbreviated to facilitate reading and save database space.

It has one, two or three components:

| Order | Name       | Description |
| ----: | ---------- | ----------- |
|     1 | Subnetwork | Meaningful subdivision of the network, for example an abbreviation high voltage DC (elec), high voltage AC, low voltage, service (water), transport, distribution, intake, high pressure (gas), low pressure, UTP (telco), coax, middle band, red light, green light. |
|     2 | Function   | A component of the subnetwork, e.g. 150kV, 400V, water quality. |
|     3 | Details    | Phase information, CH4 (high caloric), H2, channel info. |

In NetCon, the commodity is specified during the extraction.
The different components are separated with a ':' symbol.

If only a two components is specified, then these are interpreted as "Subnetwork::Details".

It is possible to specify a `secondary commodity` by typing a a ',' and then specifying the secondary commodity.
Typical secondary commodities are 'CP' for cathodic protection or 'PL' for public lighting. 

In the following table some examples are provided per network type:

| Network | Example        | Meaning                                                                                                                                                                                     |
| ------: | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|       E |                | Electric network                                                                                                                                                                            |
|       E | UHV            | ultra high voltage, default is AC                                                                                                                                                           |
|       E | UHVD           | high voltage DC                                                                                                                                                                             |
|       E | UHVD:400000    | high voltage DC, 400kV                                                                                                                                                                      |
|       E | HV             | high voltage                                                                                                                                                                                |
|       E | HV::A          | high voltage, phase A                                                                                                                                                                       |
|       E | HV::B          | high voltage, phase B                                                                                                                                                                       |
|       E | HV::C          | high voltage, phase C                                                                                                                                                                       |
|       E | HV::U          | high voltage, single (unknown) phase                                                                                                                                                        |
|       E | HV::E          | high voltage, earth wire or shield; for normal cables assumed to be there                                                                                                                   |
|       E | HV::ABC        | high voltage, phases ABC, earth shield is assumed                                                                                                                                           |
|       E | HV::ABCN       | high voltage, phases ABC and neutral, earth shield is assumed                                                                                                                               |
|       E | HV:320000:ABCN | high voltage, 320kV, phases ABC and neutral, earth shield is assumed                                                                                                                        |
|       E | HV:150000:ABCN | high voltage, 150kV phases ABC and neutral, earth shield is assumed                                                                                                                         |
|       E | HV:110000      | high voltage, 110kV phases ABC and earth shield are assumed                                                                                                                                 |
|       E | MV             | medium voltage, same high voltage examples above                                                                                                                                            |
|       E | LV             | low voltage                                                                                                                                                                                 |
|       E | LV:U           | low voltage, single (unknown) phase                                                                                                                                                         |
|       E | LV:ABC         | low voltage, phase ABC                                                                                                                                                                      |
|       E | LV:ABCN        | low voltage, phase ABC                                                                                                                                                                      |
|       E | LV:400:ABCN    | low voltage, 400 AC                                                                                                                                                                         |
|       E | LV:230:A       | low voltage, phase A, 230 AC                                                                                                                                                                |
|       E | LV:200-100:AB  | low voltage, 200 as well as 100 volt, phase AB. This should be modelled as two NetCon connections instead, one of 200V and one of 100V. This can be achieved during the extraction process. |
|       E | LV             | lowvoltage                                                                                                                                                                                  |
|       E | PL             | public lighting only                                                                                                                                                                        |
|       E | LV,PL          | lowvoltage and public lighting as secondary commodity                                                                                                                                       |
|       E | LV::ABC,PL     | lowvoltage with three phase and public lighting as secondary commodity                                                                                                                      |
|       E |                | Gas network                                                                                                                                                                                 |
|       G | HP             | high pressure gas                                                                                                                                                                           |
|       G | HP:8           | high pressure gas, 8 bar                                                                                                                                                                    |
|       G | HP:8,CP        | high pressure gas, 8 bar and Cathodic Protection as secondary commodity                                                                                                                     |
|       G | LP             | high pressure gas                                                                                                                                                                           |
|       G | LP:0.4         | low pressure gas, 0.4 bar                                                                                                                                                                   |
|       G | CP             | cathodic protection                                                                                                                                                                         |
|       H |                | Heath network                                                                                                                                                                               |
|       H | HT             | High grade temperature, > 70ᵒC at end consumers                                                                                                                                             |
|       H | MT             | Medium grade temperature, 55ᵒ - 70ᵒC at end consumers                                                                                                                                       |
|       H | LT             | Low grade temperature, < 55ᵒC at end consumers                                                                                                                                              |
|       W |                | Water network                                                                                                                                                                               |
|       T |                | Telecom network                                                                                                                                                                             |

#ToDo Write more examples.
Especially some with CP and PL.

A special case is a steel pipe transporting gas or water, that is cathodic-protected as well.
In this case, it transports gas or water on the inside, and it has a small electric current on the outside.
#ToDo

Sometimes the commodity is not registered with an asset, but it needs to be derived as a [[./Derived Commodity|Derived Commodity]].

