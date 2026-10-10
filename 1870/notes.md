---
title: Block saving users while a limit field is invalid on a hidden tab
summary: A half-typed limit (1.5) on the Limits tab is no longer saved as 1 when the admin switches tabs and presses Save.
pr: 1870
build: before upstream/main 9d37930c6; after 9d37930c6 with fix/1867-hidden-tab-limit-validation merged (255470514 desktop, 01f36feca phone)
---

Web admin, Users > Edit User > Limits. Steps: turn on the Max Streams override, type 1.5, switch to the Account tab, press Save. Before, Save sent max_streams 1 (204) and the dialog closed. After, no request is sent and the dialog returns to Limits with 1.5 still in the field. Headless Chromium does not draw the native validation bubble.

![Before: desktop, value typed](before-1-limits-typed.png)
![After: desktop, value typed](after-1-limits-typed.png)
![Before: desktop, after Save the dialog closed](before-2-after-save.png)
![After: desktop, after Save the dialog stays on Limits](after-2-after-save.png)
![Before: phone, after Save](mobile-before-3-after-save.png)
![After: phone, after Save](mobile-after-3-after-save.png)
