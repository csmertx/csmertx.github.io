---
title: Firefox: Web Browser
weight: -20
---

#### Firefox Stop Auto Updating (the workflow killer) (220308)(2203011--Firefox updated anyway...)
- sudov /etc/firefox/policies/policies.json (kubuntu 21.10)
  ```
  {
    "policies": {
        "AppAutoUpdate": false
    }
  }

  ```

#### Sources
- https://github.com/mozilla/policy-templates
