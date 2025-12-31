## How to use this template
- Overleaf: You can upload the whole folder.zip to Overleaf and compile `main.tex` directly. Notice to choose Xelatex as compiler in Overleaf settings

- Local LaTeX compilation: You can download the whole folder in zip and compile `main.tex` using `xelatex-biber-xelatex`. 
## Configuration for LaTeX Workshop
This beamer template use `xelatex-biber-xelatex` to compile. If you use Latex Workshop locally but don't have biber recipe, you can add the following recipe to your `settings.json`:
```
    "latex-workshop.latex.tools": [
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
```
Pay attention to add `biber` to `"latex-workshop.latex.tools"` if it is not already in your settings, then add the compiling chain to `"latex-workshop.latex.recipes"`:
```
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex-biber-xelatex-xelatex",
            "tools": [
                "xelatex",
                "biber",
                "xelatex",
                "xelatex"
            ]
        }
    ],
```
Restart after modifying settings.json and choose the recipe `xelatex-biber-xelatex-xelatex` to compile your beamer `main.tex` file.

## Attention
Currently this template supports English/Chinese version. You can modify font type and size in `beamerthemefudan.sty` file. 
When using this template, keep `ref.bib` , `beamerthemefudan.sty` and folder `/assets` in the same folder as your `main.tex` file. You can modify `ref.bib` to add your own references. It's used in the same way as `bibtex` but `biber` is a more powerful backend for bibliography management.


