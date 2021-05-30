NORMAL TEXT
# Heading 1
## Heading 2
### Heading 3
.
.
.\
We can break line with **2 spaces** or simply with `\`!

*Emphasized/Italic*\
_Emphasized/Italic_

**Strong/Bold**\
__Strong/Bold__

~~Overlined~~

LINK\
[Google](https://www.google.com "Hover Explanation")\
[Twitter](https://www.twitter.com "Blue Bird")
```
[Google](https://www.google.com "Hover Explanation")
[Twitter](https://www.twitter.com "Blue Bird")

```

IMAGE\
![Pirate Logo](https://brandingbycontext.com/images/nice-logo-portfolio/jack-oneill-logo-designer.jpg "Pirate")
```
![Pirate Logo](https://brandingbycontext.com/images/nice-logo-portfolio/jack-oneill-logo-designer.jpg "Pirate")
```

To resize the image it's better we use `<img>` tag in order to compensate it on all devices,\
<img src="https://brandingbycontext.com/images/nice-logo-portfolio/jack-oneill-logo-designer.jpg" alt="Pirate Logo" title="Pirate" width="220" height="220">
```html
<img src="https://brandingbycontext.com/images/nice-logo-portfolio/jack-oneill-logo-designer.jpg" alt="Pirate Logo" title="Pirate" width="220" height="220">
```

BLOCKQUOTE
>print("Blockquote")

CODE\
Inline `code word` show

```javascript
var name = "Markdown";
console.log(name);
```

```bash
git status
git add .
```

```python
"Yes" if True "No" else
```

HIDEABLE SECTION
<details>
<summary><b>This section is hideable</b></summary>

Any folded content here. It requires an empty line just above it.

</details>
<br>

TABLE
|Heading 1 |Heading 2 |Heading 3 |
|--- |--- |--- |
|00 |01 |02 |
|10 |11 |12 |
|20 |21 |22 |

The second line above is necessary with at least 3 dashes to create the table!

ITEM
- Unordered item with `-`
* Also unordered item with `*`

1. First item
1. Second item
   - Inner item with `-`
     - More inner item with `-`
     * More inner item with `*`

- Unordered item with `-`
  - Inner item with `-`
    - More inner item with `-`
    - More inner item with `-`

Above even we type numbers wrongly, it automatically writes them correctly in turn. Plus, putting **3 spaces** under an ordered item and **2 spaces** under an unordered item properly indents the below item!

HORIZONTAL LINE
***
Creates a horizontal line

---
Also creates a horizontal line

___
Also creates a horizontal line

TASK LIST
* [x] Task 1
* [ ] Task 2
* [x] Task 3