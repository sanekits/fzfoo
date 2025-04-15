# `fzf` – A Hidden Gem for Shell Scripts

[`fzf`](https://github.com/junegunn/fzf) is an interactive fuzzy finder that works on any list of text from `stdin`. It's incredibly powerful for shell scripting and CLI workflows — not just for finding files.

## 🔹 Basics

```bash
some_command | fzf
```

- Accepts any stream of lines (not just filenames)
- Displays an interactive UI
- Lets you search/filter with fuzzy matching
- Returns the selected line to `stdout`

---

## 🔹 Examples

```bash
ls | fzf
ps aux | fzf
find . -type f | fzf
```

You can then capture the result in a script:

```bash
selection=$(some_command | fzf)
```

---

## 🔹 Multi-Select

```bash
fzf --multi
```

Use with `--delimiter` and `--with-nth` for structured input.

---

## 🔹 Preview Pane

```bash
fzf --preview 'cat {}'
```

Shows a dynamic preview of the currently highlighted item.

---

## 🔹 Keybindings

```bash
fzf --bind 'ctrl-o:execute(xdg-open {})'
```

You can bind actions to keys and execute arbitrary shell commands.

---

## 🔹 Matching Modes

- Fuzzy (default): `term`
- Exact: `'term'`
- Prefix: `^term`
- Suffix: `term$`
- Exclude: `!term`
- Regex: `/term/`

---

## 🔹 Screen Behavior

- Uses the terminal's **alternate screen buffer**
- Fully restores the screen after exit — like `vim` or `less`

---

## 🔹 Summary

`fzf` is a minimalist, script-friendly UI tool for choosing from any list. If you're still using `select`, `read`, or `dialog` for line-based choices in shell scripts — `fzf` is cleaner, faster, and easier.
