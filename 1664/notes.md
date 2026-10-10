---
title: Stop saying S3 is required for artwork storage features
summary: The Appearance upload message names artwork storage (local disk or S3) instead of a public S3 bucket.
pr: 1664
build: desktop before 6e5408ae2, after 67e0c0adc; phone before upstream/main 9d37930c6, after e13753ab2
---

Web admin, Settings > Appearance. A running server reports storage_available true, so the browser loaded the real /api/v2/theme/branding response with only storage_available set to false.

![Before: desktop](before.png)
![After: desktop](after.png)
![Before: phone](mobile-before.png)
![After: phone](mobile-after.png)
