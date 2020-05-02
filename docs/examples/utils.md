---
description: Examples for usage of the utility functions for dego-py.
---

# Utils

```python
from dego import Utils

#generate_pid
payment_id = Utils.generate_pid()

print(payment_id)

#format_amount
amount = Utils.format_amount(1000)

print(amount)

#parse_amount
amount = Utils.parse_amount(1000)

print(amount)

#hexify
data = Utils.hexify(b'Super secret message')

print(data)
```

