
# Italic

```
*italic text*
```
or
```
_italic text_
```

Example: *italic*

# Bold

```
**bold text**
```
or
```
__italic text__
```

Example: **bold**


# NewLine

To add new line, either
* end a line with two or more spaces
* end the line with a '\\'
* end a line with more than one line-breaks.

From the markdown specification:
>When you do want to insert a `<br />` break tag using Markdown, you end a line with two or more spaces, then type return.

# Headings
Two levels of headings are more common.\
More levels are possible by keeping-on adding more #s.

## Heading-1
```
# Heading 1
```
or
```
Heading 1
=========
```
## Heading-2
```
## Heading 2
```
or
```
Heading 2
---------
```
# Blockquote

To quote a block of text:
```
> Blockquote
```
Large blockquote can be marked as:
```
> quote 1
>
> quote 2
```

# Inline code  (with backticks)

    Inline `code` using backticks.

# Code blocks

    ```
    # code block
    print '3 backticks or'
    ```
or

    ....# code block
    ....print 'indent 4 spaces'

- Indent using either 4 spaces, or a tab.
- Might want to ensure there is an empty line before and after the code block for the markings to work.

# Lists

## Bulleted
```
* List
* List
* List
```
or
```
- List
- List
- List
```

**Note**
Nexted bulleted lists can happen using `tab`.
```
* list1
* list2
    * nested item2.1
    * nested item2.2
```

## Numbered
```
1. One
2. Two
3. Three
```
or
```
1) One
2) Two
3) Three
```

# Links

## Web URL
```
[Link](http://a.com)
```
or
```
[Link][1]
⋮
[1]: http://b.org
```

## Image
```
![Image](http://url/a.png)
```
or
```
![Image][1]
⋮
[1]: http://url/b.jpg
```

# Horizontal rule/line
```
---
```
or
```
***
```

# Markdown with VSCode

VS Code supports Markdown files out of the box. Markdown file should have a `.md` extension.

Toggle the visualization of the editor between the code and the preview of the Markdown file by `Ctrl+Shift+V` in the editor.

Side-by-side preview with `Ctrl+K V`.

>https://code.visualstudio.com/docs/languages/markdown


# [References]

1. https://commonmark.org/help/
2. Interactive tutorial: https://commonmark.org/help/tutorial/

