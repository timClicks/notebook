An underscore can be used to create side-effects. 


```
use anyhow::{bail, format_err, Context as _};
```

This isn't as powerful as Python's `import` system, which enables imports to do anything that they want. 
