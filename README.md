# Quarto APA Narrative Citation Filter

This is a minimal Quarto filter extension designed to correct narrative APA citations by replacing the ampersand (`&`) with the word "and" in in-text narrative citations. Unlike the broader [apaquarto](https://github.com/wjschne/apaquarto) extension, this filter has a focused scope: handling narrative citations for APA-style compliance. It does not include additional formatting features or broader APA-related enhancements.

## Features

- **Correct APA Narrative Citations**: Ensures that citations follow APA style by replacing `&` with `and` in narrative citations, while leaving parenthetical citations untouched.
- **Multilingual Support**: Works with English (`en`), German (`de`), French (`fr`), and Spanish (`es`) as default languages.

## Example Usage

Here's how to use the filter in a Quarto document:

### YAML-Header (also see`example.qmd`)

```yaml
---
title: "Example document with Quarto filter extension for correct APA narrative citation"
filters:
  - apa_and_amp
bibliography: examplereferences.bib
lang: "en" # works with de, fr, and es
format:
  pdf:
    link-citations: true
  html:
    citations-hover: true
    embed-resources: true
  # typst: default
csl: https://www.zotero.org/styles/apa # For offline use or with Typst, you might want to keep CSL file in project root.
citeproc: false # Needs to be set for the filter to work. Citeproc is run by the filter.
---
```

> [!CAUTION]
> Disable Default Citeproc: To allow the filter to process citations, set citeproc: false in your document metadata.

## Installing

```bash
quarto add gwbrck/apa_and_amp
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

### Dependencies

    - Quarto (v1.4+)
    - A valid bibliography file (e.g., examplereferences.bib).
    - APA CSL file: Ensure the correct APA citation style is specified using csl. Use a local file or a URL like Zotero's APA Style.
