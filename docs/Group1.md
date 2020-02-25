---
layout: default
title: Glossary
nav_order: 11
---

# Title proper
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Element information

[Link to RDA Toolkit](https://beta.rdatoolkit.org/Content/Index?externalId=en-US_ala-4b9291c5-f525-37fd-b661-c469e763ce8a)

---

### Definition and scope

X.X A title of manifestation that is selected for preference in a specific application or context.

X.X An alternative title is treated as part of a title proper.


### Sources of information

X.X. The preferred source of information for the title proper is the title page. For special provisions relating to single-sheet manifestations, see CITATION.

X.X. Multipart monographs. If the volume is part of a multipart monograph, and the title page gives a statement of the volume or part number within the larger work, omit this statement without using the mark of omission, unless it is a grammatically inseparable part of the information being transcribed. Do transcribe statements such as “in two volumes,” however CITATION.

```Thomas Masterson his first[-second]... booke of arithmeticke```

**Source of information reads: Thomas Masterson his first[-second] booke of arithmeticke. A two-volume multipart monograph**
[OCLC: 612566303](http://www.worldcat.org/oclc/612566303)
ESTC: S112438

```Le premier[-quart] volume de messire Jehan Froissart lequel traicte des choses dignes de memoire aduenues tant es pays de France, Angleterre, Flanders, Espaigne que Escoce, et autres lieux circonuoisins```

**Source of information reads: Le premier[-quart] volume de messire Jehan Froissart lequel traicte des choses dignes de memoire aduenues tant es pays de France, Angleterre, Flanders, Espaigne que Escoce, et autres lieux circonuoisins. A four-volume multipart monograph**
[OCLC: 43092251](http://www.worldcat.org/oclc/43092251)

---

### Form and order of information

X.X Transcribe title information in the form and order in which it is presented in the source, unless instructed otherwise by specific guidelines CITATION.

X.X If parts of the title are scattered by layout or typography, compose the title proper based on those parts distinguished by position, typography, or size of lettering. If the text could reasonably be assembled in a different order, provide additional title access if considered important. 

```Our choice, Grover Cleveland, A.G. Thurman. Democratic nominees, for president, for vice president```

**Comment: Title assembled from words scattered on four banners, above and below the image**
Source: [Library of Congress](https://www.loc.gov/resource/cph.3a06060/)

X.X. If the title information is arranged decoratively, or other elements of the description (e.g., creator or publisher) are interspersed with the title information, determine the logical sequence and record the title in that order.

```The nursery frieze```

**Comment: Title constructed from letters scattered in sequence among the illustrations.**
Source: [OCLC 2013288](http://www.worldcat.org/oclc/2013288)

## Words considered part of the title proper

X.X. Title information preceding the chief title on the title page is considered part of the title proper if it is grammatically inseparable from the chief title. If the chief title is preceded or followed in the source by other elements of information, transpose these elements to their appropriate elements in the description (or give them in a note) unless case endings would be affected, the grammatical construction of the information would be disturbed, or the text is otherwise grammatically inseparable from the title proper. In the latter cases, transcribe the information as part of the title proper.

## Excluding pages

For specific pages that you do not wish to include in the main navigation, e.g. a 404 page or a landing page, use the `nav_exclude: true` parameter in the YAML front matter for that page.

#### Example
{: .no_toc }

```yaml
---
layout: default
title: 404
nav_exclude: true
---
```

---

## Pages with children

Sometimes you will want to create a page with many children (a section). First, it is recommended that you keep pages that are related in a directory together... For example, in these docs, we keep all of the written documentation in the `./docs` directory and each of the sections in subdirectories like `./docs/ui-components` and `./docs/utilities`. This gives us an organization like:

```
+-- ..
|-- (Jekyll files)
|
|-- docs
|   |-- ui-components
|   |   |-- index.md  (parent page)
|   |   |-- buttons.md
|   |   |-- code.md
|   |   |-- labels.md
|   |   |-- tables.md
|   |   +-- typography.md
|   |
|   |-- utilities
|   |   |-- index.md      (parent page)
|   |   |-- color.md
|   |   |-- layout.md
|   |   |-- responsive-modifiers.md
|   |   +-- typography.md
|   |
|   |-- (other md files, pages with no children)
|   +-- ..
|
|-- (Jekyll files)
+-- ..
```

On the parent pages, add this YAML front matter parameter:
-  `has_children: true` (tells us that this is a parent page)

#### Example
{: .no_toc }

```yaml
---
layout: default
title: UI Components
nav_order: 2
has_children: true
---
```

Here we're setting up the UI Components landing page that is available at `/docs/ui-components`, which has children and is ordered second in the main nav.

### Child pages
{: .text-gamma }

On child pages, simply set the `parent:` YAML front matter to whatever the parent's page title is and set a nav order (this number is now scoped within the section).

#### Example
{: .no_toc }

```yaml
---
layout: default
title: Buttons
parent: UI Components
nav_order: 2
---
```

The Buttons page appears as a child of UI Components and appears second in the UI Components section.

### Auto-generating Table of Contents

By default, all pages with children will automatically append a Table of Contents which lists the child pages after the parent page's content. To disable this auto Table of Contents, set `has_toc: false` in the parent page's YAML front matter.

#### Example
{: .no_toc }

```yaml
---
layout: default
title: UI Components
nav_order: 2
has_children: true
has_toc: false
---
```

### Children with children
{: .text-gamma }

Child pages can also have children (grandchildren). This is achieved by using a similar pattern on the child and grandchild pages.

1. Add the `has_children` attribute to the child
1. Add the `parent` and `grand_parent` attribute to the grandchild

#### Example
{: .no_toc }

```yaml
---
layout: default
title: Buttons
parent: UI Components
nav_order: 2
has_children: true
---
```

```yaml
---
layout: default
title: Buttons Child Page
parent: Buttons
grand_parent: UI Components
nav_order: 1
---
```

This would create the following navigation structure:

```
+-- ..
|
|-- UI Components
|   |-- ..
|   |
|   |-- Buttons
|   |   |-- Button Child Page
|   |
|   |-- ..
|
+-- ..
```

---

## Auxiliary Navigation

To add a auxiliary navigation item to your site (in the upper right on all pages), add it to the `aux_nav` [configuration option]({{ site.baseurl }}{% link docs/configuration.md %}#aux-nav) in your site's `_config.yml` file.

#### Example
{: .no_toc }

```yaml
# Aux links for the upper right navigation
aux_links:
  "Just the Docs on GitHub":
    - "//github.com/pmarsceill/just-the-docs"
```

---

## In-page navigation with Table of Contents

To generate a Table of Contents on your docs pages, you can use the `{:toc}` method from Kramdown, immediately after an `<ol>` in Markdown. This will automatically generate an ordered list of anchor links to various sections of the page based on headings and heading levels. There may be occasions where you're using a heading and you don't want it to show up in the TOC, so to skip a particular heading use the `{: .no_toc }` CSS class.

#### Example
{: .no_toc }

```markdown
# Navigation Structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
```

This example skips the page name heading (`#`) from the TOC, as well as the heading for the Table of Contents itself (`##`) because it is redundant, followed by the table of contents itself.
