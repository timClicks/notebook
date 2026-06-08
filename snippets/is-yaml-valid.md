# Is this a valid YAML file?

"Valid" here means that the input is not empty and is the syntax is spec-compliant.

```python
import pathlib
import yaml

def is_valid_yaml(path: pathlib.Path):
    with open(path) as f:
        data = yaml.safe_load(f)
        if data:
            return True
    return False
```
