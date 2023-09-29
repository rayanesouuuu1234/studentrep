---
toc: True
comments: True
layout: post
title: Emoji
description: None
courses: {'csp': {'week': 2}}
type: hacks
---

```python
from IPython.display import display, HTML
from emoji import emojize

output = emojize(":soccer_ball: Soccer is awesome! Messi>Ronaldo :goal_net:")
display(HTML(f"<span style='font-size: 20px;'>{output}</span>"))
```


<span style='font-size: 20px;'>⚽ Soccer is awesome! Messi>Ronaldo 🥅</span>

