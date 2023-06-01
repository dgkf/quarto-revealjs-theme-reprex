# `SCSS` errors when using revealjs within a webpage

Including a presentation within a webpage seems to hit regular SCSS issues. 

What led me to create this minimal working example was an issue with another
project failing to discover SCSS files. Reducing the problem further, this
project fails due to undefined variables unrelated to the one variable that I
set.

Running `quarto preview` hits the error:

```
> quarto preview
Preparing to preview
[1/2] presentation.qmd
[2/2] index.qmd
ERROR: Theme file compilation failed:

Error: $color: null is not a color.
    ╷
885 │   $red: _linear-channel-value(quarto-color.red($color));
    │                               ^^^^^^^^^^^^^^^^^^^^^^^^
    ╵
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 885:31  luminance()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 895:13  contrast()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 912:19  tone()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 657:7   theme-contrast()

Stack trace:

Error: $color: null is not a color.
    ╷
885 │   $red: _linear-channel-value(quarto-color.red($color));
    │                               ^^^^^^^^^^^^^^^^^^^^^^^^
    ╵
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 885:31  luminance()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 895:13  contrast()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 912:19  tone()
  /var/folders/1d/zfy2f_ms289fy73937h1l0xr0000gp/T/quarto-sessiondb58edd1/d1565598/181bafef.scss 657:7   theme-contrast()
    at dartCommand (file:///Users/kelkhofd/Projects/quarto-cli/src/core/dart-sass.ts:102:11)
    at eventLoopTick (ext:core/01_core.js:181:11)
    at async dartCompile (file:///Users/kelkhofd/Projects/quarto-cli/src/core/dart-sass.ts:52:3)
    at async compileWithCache (file:///Users/kelkhofd/Projects/quarto-cli/src/core/sass.ts:330:9)
    at async compileSass (file:///Users/kelkhofd/Projects/quarto-cli/src/core/sass.ts:129:10)
    at async resolveSassBundles (file:///Users/kelkhofd/Projects/quarto-cli/src/command/render/pandoc-html.ts:128:21)
    at async resolveExtras (file:///Users/kelkhofd/Projects/quarto-cli/src/command/render/pandoc.ts:1208:14)
    at async runPandoc (file:///Users/kelkhofd/Projects/quarto-cli/src/command/render/pandoc.ts:354:20)
    at async renderPandoc (file:///Users/kelkhofd/Projects/quarto-cli/src/command/render/render.ts:197:24)
    at async Object.onRender (file:///Users/kelkhofd/Projects/quarto-cli/src/command/render/render-files.ts:567:30)
```
