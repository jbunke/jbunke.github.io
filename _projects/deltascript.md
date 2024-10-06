---
title: DeltaScript
description: "A lightweight scripting language skeleton designed to be easily extended for the specification and implementation of domain-specific languages"
gh-link: "https://github.com/jbunke/deltascript"
status: "In development"
start-year: 2024
end-year: 2024
index: 1
---

<!-- TODO -->
Example code:

```js
(string s -> string) {
    string rev = "";

    for (c in s)
        rev = c + rev;

    return rev;
}
```

And much more...
