# QField Ecosystem Status page

See also:

* Example site repository link (you are here): https://github.com/cstate/example
* Main cState source code repository: https://github.com/cstate/cstate

## Adding and updating an incident

1. create a new file in `content/issues` with the name `[yyyy-mm-dd]-incident.md`
2. copy the following block. Make sure to replace the `[yyyy-mm-dd  hh:MM:00]`
   with the incident/update date and time in exactly this format and UTC!

```
---
title: Degraded service
date: yyyy-mm-dd hh:MM:00  # In UTC, see https://www.utctime.net/
resolved: false
# resolvedWhen: [yyyy-mm-dd hh:MM:00]
# Possible severity levels: down, disrupted, notice
severity: down
affected: # See systems in https://github.com/opengisch/qfieldcloud-status/blob/master/config.yml
  - app.qfield.cloud
section: issue
---

<!-- *Resolved* -
We believe all users experiencing issues have been able to connect at this time. {{< track "yyyy-mm-dd hh:MM:00" >}}

*Monitoring* -
We believe the connectivity issues are being caused by an isolated ISP issue. We've had reports that swapping to Google DNS servers (see here; https://developers.google.com/speed/public-dns/docs/using) resolves the problem for users. {{< track "yyyy-mm-dd hh:MM:00" >}}
-->
*Investigating*
- We're aware of reports that users are experiencing some random problems. We're currently investigating these issues, and apologize for any inconvenience it may be causing you. {{< track "yyyy-mm-dd hh:MM:00" >}}
```

3. uncomment / update as information becomes available / issues are fixed
4. uncomment / updated `resolvedWhen` set `resolved` to `true`

## Adding and updating a planned maintenance

1. create a new file in `content/issues` with the name `[yyyy-mm-dd]-maintenance-window.md`
2. copy the following block. Make sure to replace the `[yyyy-mm-dd  hh:MM:00]`
   with the planned date in exactly this format and UTC!

```
---
title: Maintenance Announcement 
date: [yyyy-mm-dd  hh:MM:00] # In UTC, see https://www.utctime.net/
informational: true
pin: true
section: issue
---

We will upgrade app.qfield.cloud to the latest release.
Expected duration: 2 hours.
```

3. when you are done, set `pin` to `false`

## Are you updating? Use these commands

Download your site with all the directories. `git clone --recursive <your repo link goes here>`

Update the cState theme submodule. `git submodule foreach git pull origin master`

In the parent directory, type `hugo serve`. Check to see if everything is working.

Then do `git add -A; git commit -m "Update cState"; git push origin <branch, probably main or master>`. Your status page is now updated and uploaded.


## For maintainers (probably not for you)

Maintainers need to update both cstate/cstate and cstate/example for each new version.

Download this repo with all the directories. `git clone --recursive -b master https://github.com/cstate/example.git`

Add your changes from cstate/cstate's exampleSite folder.

Update the cState theme submodule. `git submodule foreach git pull origin master`

Then push `git add -A; git commit -m "Update cState vX.X.X"; git push origin master`.

## License

MIT © Mantas Vilčinskas
