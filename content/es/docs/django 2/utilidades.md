---
title: "Utilidades"
date: 2021-10-21T10:36:54+02:00
weight: 20
description: >
  
tags: []
---

{{% pageinfo %}}
* https://pypi.org/project/python-dotenv/
{{% /pageinfo %}}

```bash
$ pip install python-dotenv
```

```bash
# .env
USER=admin
```


```python
import os
from dotenv import load_dotenv

load_dotenv()  # take environment variables from .env.
USER = os.getenv("USER")

```

