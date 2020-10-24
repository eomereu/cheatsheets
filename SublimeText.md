## Sublime Text 3

- Hitting *Tab* after typing `html` in Sublime, creates the boilerplate automatically for us. (After giving the file *.html* extension)

- Simply to fastly create a comment, select the content or go on a line and hit **`Ctrl + /`**

- In order to create multiple cursors in Sublime, simply hold Ctrl and click on places that we want the cursor to be on.

- **`Ctrl + Shift + D`** automatically copies the current line and pastes on next line directly.

- Typing `lorem` and hitting Tab right after it, is going to give a long text to us, automatically.

- **`Ctrl + L`** selects the current line 

- To go to end and the beginning of a line in Sublime with "Alt+Right"/"Alt+Left"; paste the following into the Key Bindings within Preferences:
```
{ "keys": ["alt+left"], "command": "move_to", "args": {"to": "bol", "extend": false} },
{ "keys": ["alt+right"], "command": "move_to", "args": {"to": "eol", "extend": false} }
```

- **`Shit + Tab`** takes the selected lines 1 intend backwards.

- **`Ctrl + D`** selects all the instances of a selected text one by one on each push within Sublime Text 3, which will implicitly duplicate the cursor. It's better to choose the text from beginning to end by letting the cursor be at the end not at on the front!