# Quarto RevealJS bug reprex

Custom themes appear to not be populated using revealjs, and file discovery
apperas quite flaky.

For a while, I would get errors as SCSS fails to find `_variables.scss`, but
only if a revealjs presentation was _nested_ inside of another file. 

```
> quarto preview presentation.qmd
```

Would build without error, while

```
> quarto preview examples/presentation.qmd

ERROR: Theme file compilation failed:

Error: Can't find stylesheet to import.
   ╷
46 │ @import "variables";
   │         ^^^^^^^^^^^
   ╵
```

Would fail to import the appropriate themes.

That issue seemed to disappear after running

```
rm -rf _site .quarto examples/presentation_files
```

Nevertheless, this difference seems to underpin a deeper issue that quarto might
be ignoring the qmd file path when searching for theme files.

After deleting those files, the whole project builds without error, which is
equally disconcerting, given that the `_variables.scss` currently attempts to
import a file that doesn't exist.
