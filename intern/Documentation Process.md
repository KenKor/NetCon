---
title: DocumentationProcess
description: Steps to product and publish the documentation
permalink: 
aliases: 
draft: true
date: 2024-09-30
share: false
tags: 
---
# Documentation Process

The documentation process should be:

* Trustable
* Have the documentation content registered in the git version control with the source code
* Be built on standard components
* Support:
	* Branding
	* Search
	* Translation
	* Reuse of shared content
* Scale

The process that has been currently drafted is depicted below:

```mermaid
graph LR
  subgraph Develop
    code([Source Code])
    doc([Documentation Content])
    sg[(Solution Git)]
  end
  doc-->|enveloppe|pgm
  subgraph Layout
    pgm([Content in Main])-->|merge|pg4([Content + Styling in v4])
    pg[(Publish Git)]
  end
  pg4-->|quartz|web
  subgraph Host
    web([Documentation Web Site])
  end
```

Remarks:

* Working together
