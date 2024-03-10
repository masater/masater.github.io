# Introduction to Markdown Syntax

A file ending with ".md " is a markdown file. Markdown is a lightweight markup language - a language that describes to a computer how text is formatted, structured, etc.  
Markdown is commonly used for README files to document important information about projects in the software sector, engineering sector, and many more. Markdown can be converted into other markup languages, such as HTML. 
The following contains a quick guide to the basic markdown syntax:

## Titles

Titles and subtitles are created with a `#`-prefix. The number of `#` indicates the (sub)title level.

```markdown
# Title
## Subtitle
### Subsubtitle
```
**Note:** The `#`-prefix applies to everything that follows in the same line, but only if there is a space (' ') between it and the text, e.g., "# Title" and not "#Title".

## Plain Text and New Line

Plain text can written directly into the .md file.  
To start a new line, leave two spaces "  " at the end of the existing line and write the new line on the next line in your markdown file.

## Emphasis

For **bold** and *italic* text use:  

```markdown
*italic* or _italic_
**bold** or __bold__
```

## Lists
**Ordered lists** are done via:  
```markdown
1.I
2. am
3. ordered
  1. with
  2. subitems
```
giving the following output:  
1. I
2. am
3. ordered

**Unordered lists** are done via:  
```markdown
- I
- am
- unordered
  - with
  - subitems
```
which yields:  
- I
- am
- unordered
  - with
  - subitems
 
## Links and Images

Links and images can be inserted via:  
```markdown
[Link text](URL)
![Alt text](Image URL)
```

## Inline Code and Code Blocks

For inline code, use single backticks. For code blocks, use triple backticks or indent with four spaces.  
**Note 1:** A backtick being ` and **not** '. On my keyboard, the single backtick ` is written by pressing "shift + ^".  
**Note 2:** Close the inline code block by putting the single backtick or triple back tick at the end, respectively.  
**Note 3:** Specify display styles my writing the language next to the three backticks.  
```markdown
`inline code`

```python
def function():
    return "Code block"
```


> Note: Remove the additional spaces before the closing triple backticks in the actual Markdown file.

## Blockquotes

Prefix text with `>` to create a blockquote.

```markdown
> This is a blockquote.
```



