## Usage

```bash
pandoc -t markdown_strict --citeproc nocite.md -o out.md --bibliography crypto.bib --csl=apa-no-ampersand.csl
```

Assumes .csl file is available, otherwise

```bash
wget https://github.com/citation-style-language/styles/raw/refs/heads/master/apa-no-ampersand.csl
```

## Pandoc --citeproc .md
https://pandoc.org/MANUAL.html#citation-rendering
- -f: from (source file type)
- -t: to (out file type)
- -s: create a “standalone” file, with a header and footer, not just a fragment

https://citeproc-js.readthedocs.io/en/latest/csl-json/markup.html

May wish to look into cryptobib https://cryptobib.di.ens.fr/

## Cytation Style Language (CSL)
https://github.com/citation-style-language
Get .csl files from https://github.com/citation-style-language/styles-distribution
E.g., https://raw.githubusercontent.com/citation-style-language/styles-distribution/f8524f9b9df60e94e98f824f242a1fb27cc9fc59/springer-lecture-notes-in-computer-science.csl
https://raw.githubusercontent.com/citation-style-language/styles-distribution/f8524f9b9df60e94e98f824f242a1fb27cc9fc59/springer-lecture-notes-in-computer-science-alphabetical.csl

## Nocite whole .bib
https://tex.stackexchange.com/questions/610876/generating-markdown-from-bib-file

Create a base.md:

```markdown
---
bibliography: crypto.bib
link-bibliography: false
nocite: "@*"
---
```


```bash
pandoc -t markdown_strict --citeproc base.md -o bib-out.md --bibliography sample.bib --csl=style.csl
```

## Citations in individual .md
https://discourse.gohugo.io/t/how-can-i-manage-a-publication-list-in-hugo-preferrably-from-bibtex-file/2089/9

```bash
pandoc -s -t markdown-citations --citeproc input.md --bibliography sample.bib --csl style.csl -o out.md
```