# babel-plugin-html-tag

Statically evaluates and minifies tagged `` html`<..>` `` template literals into strings

## What it does:

Minifies tagged template literals (by default using `html` tag) via `html-minifier` then removes the tag:

In:

```js
const a = html`<p class="zoom center justify">
    This is paragraph with ${b} subsitutions 
    at several lines: ${1 + 2}
</p>`;

const z = html`<table class="center">
    <tr class='left'>
        <td>HTML without substitutions</td>
    </tr>
</table>`;
```

Out:

```js
const a = `<p class="zoom center justify">This is paragraph with ${b} subsitutions at several lines: ${1 +
  2}</p>`;

// becomes static one line string if there is no substitutions
const z =
  '<table class="center"><tr class="left"><td>HTML without substitutions</td></tr></table>';
```