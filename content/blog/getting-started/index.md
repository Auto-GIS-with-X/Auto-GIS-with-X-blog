---
title: Getting Started...
date: 2021-05-08
description: Setting up the Python, R, Julia, and Rust packages.
---
## Julia

At the recommendation of the [Pkg](https://pkgdocs.julialang.org/v1/creating-packages/) docummentation, I used the [PkGTemplates](https://invenia.github.io/PkgTemplates.jl/stable/) package to generate the Julia [AutoGIS](https://github.com/Auto-GIS-with-X/Auto-GIS-with-Julia) package structure.

I used the interactive approach...

```julia
using PkgTemplates
Template(interactive=true)("AutoGIS")
```

... and stuck to the defaults with the following exceptions:

- I disabled [TagBot](https://github.com/JuliaRegistries/TagBot) because I don't expect to release this package
- I enabled [GitHub Actions](https://github.com/features/actions) for CI and [Codecov](https://codecov.io/) to report test coverage because I use them regularly at work
- I enabled [Documenter](https://github.com/JuliaDocs/Documenter.jl) because I want to practice documenting a Julia package
- I enabled [Develop](https://invenia.github.io/PkgTemplates.jl/stable/user/#PkgTemplates.Develop) because it seem like a good idea

I already had the [Julia VS-Code pulgin](https://github.com/julia-vscode/julia-vscode) installed but I took the advice offered in the [Blue](https://github.com/invenia/BlueStyle) Style Guide and added the following to my editor settings:

```js
{
    "[julia]": {
        "editor.detectIndentation": false,
        "editor.insertSpaces": true,
        "editor.tabSize": 4,
        "files.insertFinalNewline": true,
        "files.trimFinalNewlines": true,
        "files.trimTrailingWhitespace": true,
        "editor.rulers": [92],
    },
}
```

Once I'd do that I just needed to activate the package to start adding dependencies:

```julia
Pkg.activate(".")
```