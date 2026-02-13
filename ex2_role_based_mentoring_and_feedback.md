## Ask the model to act as a coding mentor.
**_prompt_**
**_response_**

## Provide a simple piece of code (e.g., a Python function with a bug).
**_prompt_**


**_response_**

## Prompt the model: 
**_prompt_**
```
Act as a mentor reviewing this code. Provide corrections and explain improvements.

import jupyter
import numpy 
import pandas

print('Hello, World!';)
```


**_response_**

```
🔍 Issues & Corrections
1️⃣ import jupyter ❌
Problem:

jupyter is not typically imported inside Python scripts.

Jupyter is an environment (Notebook/Lab), not a library you normally import.

If this runs in a normal Python file, it may fail.

Fix:

Remove it unless you specifically need a Jupyter-related module.

# remove this
# import jupyter

2️⃣ import numpy and import pandas ⚠️
Problem:

You imported libraries but didn’t use them.

Unused imports:

Slow down startup slightly

Reduce readability

Fail linting checks (e.g., flake8, pylint)

Signal poor code hygiene

Fix:

Only import what you use.

If you're not using them:

# Remove unused imports

If you plan to use them, follow convention:

import numpy as np
import pandas as pd


Using aliases (np, pd) is standard in the Python ecosystem.

3️⃣ Syntax Error in print() ❌

Your line:

print('Hello, World!';)

Problem:

You placed a semicolon inside the parentheses.

Correct syntax:

print('Hello, World!')


In Python:

Semicolons are optional.

They are used to separate multiple statements on one line.

They do NOT go inside function arguments.

✅ Cleaned Version (Minimal)
print("Hello, World!")


That’s all you need.

💡 Mentor-Level Improvements

Even for simple scripts, practice writing production-quality code.

1️⃣ Add a main guard (good habit)
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()


Why?

Makes your script reusable

Prevents accidental execution when imported

Builds backend engineering discipline

Since you're transitioning toward backend and DevOps, this habit matters.

2️⃣ If This Was a Data Script

If your goal was to start a data project:

import numpy as np
import pandas as pd

def main():
    print("Libraries loaded successfully")

if __name__ == "__main__":
    main()


Only import what you actually use.
```

## Review the response and check if the role influences feedback style.

Yes the role influenced the response style. The response was in form of a teacher reviewing a work step-by-step and providing corrections at the end. It also gave advice on how to make it better by following the standard way of writing code.