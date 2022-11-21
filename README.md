# `SCSS` compilation failure with revealjs

Using `@import` scss directive with html works fine

```yml
format: custom-html
```

But fails when using revealjs

```yml
format: custom-revealjs
```
```
ERROR: Theme file compilation failed:

Error: Can't find stylesheet to import.
   ╷
46 │ @import "scss/variables";
   │         ^^^^^^^^^^^
   ╵
```
