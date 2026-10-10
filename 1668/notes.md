---
title: Inherited policy selects fit their label
summary: Edit User selects for inherited policies show the full "Server default" value instead of cutting it off, and wrap inside narrow dialogs.
pr: 1668
build: before upstream/main 9d37930c6; after 9d37930c6 with fix/1398-inherited-policy-select-width (047f6bb29) merged
---

Web admin, Users > Edit User > Access, for a user in "No group". Local dev build, dummy data.

![Before: desktop, inherited values cut off](before-access.png)
![After: desktop, full labels](after-access.png)
![Before: 320px wide, dialog overflows](before-320-access.png)
![After: 320px wide, labels wrap inside the select](after-320-access.png)
