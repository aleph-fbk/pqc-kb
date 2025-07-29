## Install and test locally

Following Hugo installation instructions ([Linux](https://gohugo.io/installation/linux/)):

```bash
sudo snap install hugo
hugo mod get -u
hugo server -D
```

## New content

From terminal:

```bash
hugo new content content/path/filename.md
```

This will use the (default) archetype, populating the new file with typical frrontmatter.

## Images

If an image appears only on one page, bundle it with that page. See [Hugo](https://gohugo.io/content-management/page-bundles/#leaf-bundles), [Hextra](https://imfing.github.io/hextra/docs/guide/organize-files/#add-images) guides.

If an image is clear to read in light or dark mode, rather than creating a new one for the other mode consider applying a color inversion filter. For example, rather than

```markdown
![circuit](/images/Hadgate.png)
```
use

```markdown
<img class="light-invertible" src="../images/Hadgate.png" alt="Hadamard gate circuit"/>
```

If the image was created with dark mode in mind, use `class="dark-invertible"` instead.

Bonus points: make the background transparent, rather than white (or other solid color).

## Bibliography

To add bibliographic references with a uniform style throughout, use [pandoc](https://github.com/jgm/pandoc) and [CSL](https://github.com/citation-style-language/styles) to generate footnote markdown.

Create or modify `.bib` files in `assets/bib/`. Check the readme in that folder for more details.
By way of example, use

```bash
pandoc -t markdown_strict --citeproc nocite.md -o bib-out.md --bibliography standards.bib --csl=apa-no-ampersand.csl
```