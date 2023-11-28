# Glossary Extension for Quarto

<!-- Link to current CSS file for styling -->
<link href="https://debruine.github.io/quarto-glossary/index_files/libs/quarto-contrib/glossary/glossary.css" rel="stylesheet"></link> 

This extension provides shortcodes for [glossary](https://debruine.github.io/glossary/) in quarto.

## Installing

```sh
quarto install extension debruine/quarto-glossary
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.


## Glossary file

You can store definitions in a YAML file. Use markdown to create paragraphs, links, and lists. Make sure each new line in a definition is indented two spaces (sorry YAML is a bit picky, but it's the best human-editable solution).

```
SESOI: |
  Smallest Effect Size of Interest: the smallest effect that is theoretically or practically meaningful
quarto: |
  An open-source scientific and technical publishing system
power: |
  The probability of rejecting the null hypothesis when it is false, for a specific analysis, effect size, sample size, and criteria for significance.
```

## Terms

Mark terms to be defined in the text like below:

| Code | Display |
|------|---------|
| `{{< glossary quarto >}}` | <button class="glossary"><span class="def">An open-source scientific and technical publishing system</span>power</button> |
| `{{< glossary power popup="hover" >}}` | <button class="glossary" title="The probability of rejecting the null hypothesis when it is false, for a specific analysis, effect size, sample size, and criteria for significance.">power</button> |
| `{{< glossary SESOI popup="none" >}}` | <button class="glossary" title="Smallest Effect Size of Interest: the smallest effect that is theoretically or practically meaningful">SESOI</button> |

## Table

You can display a glossary table containing all of the words you've marked with this code:

`{{< glossary table=true >}}`

<table class="glossary_table"><tbody><tr><th> Term </th><th> Definition </th></tr><tr><td>power</td><td>The probability of rejecting the null hypothesis when it is false, for a specific analysis, effect size, sample size, and criteria for significance.</td></tr><tr><td>sesoi</td><td>Smallest Effect Size of Interest: the smallest effect that is theoretically or practically meaningful</td></tr><tr><td>quarto</td><td>An open-source scientific and technical publishing system</td></tr></tbody></table> |

More examples: <https://debruine.github.io/quarto-glossary>
