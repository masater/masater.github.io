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
## Commenting Out Signs
To display a certain sign or sign combination, such as "\*\*bold\*\*", as plain text use "\\"sign in front of it:
```markdown
 \*\*bold\*\*
```

## Lists
**Ordered lists** are done via:  
```markdown
1. I
2. am
3. ordered
  1. with
  2. subitems
```
yielding the following output:  
1. I
2. am
3. ordered
  1. with
  2. subitems

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
```markdown
`inline code`
\```
Code
Block
\```
```  
> **Note 1:** A backtick is \` and **not** '. On my keyboard, the single backtick \` is written by pressing "shift + ^".  
Close the inline code block by putting the single backtick or triple backtick at the end, respectively. In general the number of backticks can be varied arbitrarily, as long as the box is closed with the same number of backticks.  
Inside the Codeblock the text will be displayed as either plain text or in the style specified after the initial three backticks:
````markdown
```markdown
I am a markdown code block.
Isn't this cool?
```
````
yielding:
```markdown
I am a markdown code block.
Isn't this cool?
```

or for python:
`````
```python
def function():
    return "Code block"
```
`````
yielding:
```python
def function():
    return "Code block"
```
> **Note**: Make sure to close code blocks with their respective number of backticks on a new line without spaces. This is because the program reading and displaying the file to you, expects the block to be closed in such a manner. If it encounters unexpected spaces like that can cause formatting issues.

## Blockquotes

Prefix text with ">" to create a blockquote.
```markdown
> This is a blockquote.
```
which yields:
> This is a blockquote.



