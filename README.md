# Glossary Extension for Quarto

<style>
.glossary {
  color: purple;
  text-decoration: underline;
  cursor: help;
  position: relative;
  border: none;
  padding: 0;
}

/* only needed for popup = "click" */
/* popup-definition */
.glossary .def {
  display: none;
  position: absolute;
  z-index: 1;
  width: 200px;
  bottom: 100%;
  left: 50%;
  margin-left: -100px;
  background-color: #333;
  color: white;
  padding: 5px;
  border-radius: 6px;
}
/* show on click */
.glossary:active .def {
  display: inline-block;
}
/* triangle arrow */
.glossary:active .def::after {
  content: ' ';
  position: absolute;
  top: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: #333 transparent transparent transparent;
}

/* glossary table styles */
.glossary_table td {
  vertical-align: top;
}

.glossary_table td:first-child {
  padding-right: 1em;
}

.glossary_table tr {
  border-bottom: 1px solid #ddd;
}

.glossary_table tr:nth-child(even) {
  background-color: #99999933;
}

</style>

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
| `{{< glossary quarto >}}` | <button class="glossary"><span class="def">An open-source scientific and technical publishing system</span>quarto</button> |
| `{{< glossary power popup="hover" >}}` | <button class="glossary" title="The probability of rejecting the null hypothesis when it is false, for a specific analysis, effect size, sample size, and criteria for significance.">power</button> |
| `{{< glossary SESOI popup="none" >}}` | <button class="glossary" title="Smallest Effect Size of Interest: the smallest effect that is theoretically or practically meaningful">SESOI</button> |

## Table

You can display a glossary table containing all of the words you've marked with this code:

`{{< glossary table=true >}}`

<table class="glossary_table"><tbody><tr><th> Term </th><th> Definition </th></tr><tr><td>power</td><td>The probability of rejecting the null hypothesis when it is false, for a specific analysis, effect size, sample size, and criteria for significance.</td></tr><tr><td>sesoi</td><td>Smallest Effect Size of Interest: the smallest effect that is theoretically or practically meaningful</td></tr><tr><td>quarto</td><td>An open-source scientific and technical publishing system</td></tr></tbody></table> |

More examples: <https://debruine.github.io/quarto-glossary>
