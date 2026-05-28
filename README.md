# PHYS3071 Astrophysics — Course Notes

[![CC BY-NC-SA 4.0][cc-shield]][cc]

LaTeX source for the PHYS3071 Astrophysics course notes at HKUST.

## Structure

```
phys3071/
├── main.tex             # Main document — compile this
├── preamble.tex         # Packages, colours, custom environments
├── references.bib       # Bibliography database
├── compile.sh           # Compilation script (macOS / TeX Live)
├── README.md            # This file
├── chapters/
│   ├── intro.tex        # Introduction & document conventions
│   ├── appendix.tex     # Declarations, mathematical tools, constants
│   └── questions.tex    # Practice questions (placeholder)
└── images/              # Add figures here
└── code/                # Add code examples here
```

## How to Compile

### Quick (recommended)

```bash
cd phys3071/
./compile.sh
```

This uses `latexmk` if available (automatic multi-pass), otherwise falls
back to a manual 4-pass sequence: `pdflatex → biber → pdflatex → pdflatex`.

### Other options

| Command | What it does |
|---|---|
| `./compile.sh` | Compile once and produce `main.pdf` |
| `./compile.sh --open` | Compile and open the PDF (macOS only) |
| `./compile.sh --watch` | Watch for changes and recompile automatically (requires `latexmk`) |
| `./compile.sh --clean` | Remove all auxiliary build files |

### Manual compilation

If the script doesn't work on your system:

```bash
pdflatex main
biber main
pdflatex main
pdflatex main
```

## Requirements

- A TeX distribution (TeX Live 2025+ recommended)
  - Install via [MacTeX](https://tug.org/mactex/) (macOS) or
    `sudo apt install texlive-full` (Linux)
- Packages: `tcolorbox`, `tikz`, `biblatex`, `amsmath`, `microtype`, etc.
  (all are included in a full TeX Live installation)

## Adding New Content

1. Create a new chapter file: `chapters/ch01_topic_name.tex`
2. Add `\input{chapters/ch01_topic_name}` in `main.tex` (after the intro)
3. Add images to `images/` and reference them as `\includegraphics{filename}`
4. Add bibliography entries to `references.bib`

## License

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc].

[cc]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
