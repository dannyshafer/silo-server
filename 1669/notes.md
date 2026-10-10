---
title: Allow canceling image cache cleanup jobs
summary: Image cache cleanup jobs can be canceled from the v2 API, and Job History shows the deletion totals of a canceled cleanup.
pr: 1669
build: backend aca4f2c4d for both; web before upstream/main 9d37930c6, web after aca4f2c4d
---

Web admin, Maintenance > Job History, same backend and same canceled cleanup job, only the web build differs. The job row was inserted with psql over dummy prefixes in the local artwork store, because a real one is only queued after deleting a library with cached artwork.

![Before: desktop, canceled row shows no totals](jobhistory-before.png)
![After: desktop, canceled row shows deletion totals](jobhistory-after.png)
![Before: phone](jobhistory-before-mobile.png)
![After: phone](jobhistory-after-mobile.png)

Cancel API, before (upstream/main): cancelable false, cancel returns 409 job_not_cancelable, job runs to succeeded. After: cancelable true, cancel returns 202 canceling, job ends canceled with deleted_prefixes 55860 of 60000.
