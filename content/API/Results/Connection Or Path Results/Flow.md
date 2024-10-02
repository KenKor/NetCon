---
title: Flow
description: "'DownStream' if the commodity flow from FromId towards ToId, 'Mazed' if the networks barriers are such that the flow can go both ways, 'NoFlow' if no connected path to a [[Sources|Source]] exists, see also [[Role|Role]]. Note that you should never see 'UpStream' in API call results since this is just 'DownStream' with the from and to id swapped."
Type: string
Order: 999
Unique: false
permalink: 
aliases: 
draft: false
date: 2024-09-30
tags:
  - ApiResult
  - Flow
  - ToDo
---
# Flow

Type of: _string_
Unique: __

'DownStream' if the commodity flow from FromId towards ToId, 'Mazed' if the networks barriers are such that the flow can go both ways, 'NoFlow' if no connected path to a [[Sources|Source]] exists, see also [[Role|Role]]. Note that you should never see 'UpStream' in API call results since this is just 'DownStream' with the from and to id swapped.

#ToDo Source tracing-cause-analysis-or-upstream.