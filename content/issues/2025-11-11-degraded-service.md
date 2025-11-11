---
title: Degraded service
date: 2025-11-11 13:35:00
# Possible severity levels: down, disrupted, notice
resolved: true
resolvedWhen: 2025-11-11 15:20:00
severity: disrupted
affected: # See systems in https://github.com/opengisch/qfieldcloud-status/blob/master/config.yml
  - app.qfield.cloud
section: issue
---

*Resolved*
- Our upstream provider had a network issue that prevented QFieldCloud instances from reaching the backend databases. A faulty switch was identified and replaced, and network connectivity has been restored.
- All QFieldCloud Dedicated instances are reachable again.

*Investigating*
- We are experiencing a service degradation on app.qfield.cloud and some dedicated QFieldCloud instances. We can see interrupted network connectivity between QFieldCloud and the backend database. We are investigating and in contact with our upstream provider.
