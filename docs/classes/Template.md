---
layout: default
title: "Template class"
parent: "Class reference"
---

# Template Class

**Brief:** provides a render template

## Detailed description

A template consists of a list of nodes, each node being of the 3 following types:

- text
- tag ({% raw %}{%{% endraw %} %})
- object ({% raw %}{{{% endraw %} }})

Text nodes are copied verbatim to the output.

Tag nodes represents instructions and allow control flow to alter the output.

Object nodes are variables are expressions that are ultimately converted to a string and inserted into the output string.

If you use the built-in parser to create a Template, the following tags are supported:

- assign
- capture
- for
- if
- break
- continue
- eject
- discard
- include
- newline

## Members documentation

### const std::string& filePath() const

**Brief:** returns the template's file path

This function returns the filepath that was passed through the constructor.

### const std::string& source() const

**Brief:** returns the original source of the template

### std::string render(const liquid::Map& data) const

**Brief:** renders the template

Parameters:
- rendering data

This function uses the default Renderer.

### std::pair\<int, int> linecol(size_t off) const

**Brief:** returns the line an column number of the character at a given offset

Parameters:
- offset in bytes

### std::string getLine(size_t off) const

**Brief:** returns the line containing the character at a given offset

Parameters:
- offset in bytes

### void lstrip(std::string& str)

**Brief:** removes whitespaces at the beginning of string

Parameters:
- input string

### void rstrip(std::string& str)

**Brief:** removes trailing whitespaces from the string

Parameters:
- input string

### void stripWhitespacesAtTag()

**Brief:** removes extra whitespaces from the template

This function removes whitespaces before and after each 'tag' node.

### void skipWhitespacesAfterTag()

**Brief:** removes extra whitespaces from the template

This function removes whitespaces after each 'tag' node.

## Non-Members documentation

### Template parse(const std::string& str, std::string filepath)

**Brief:** parse a template

Parameters:
- template source
- optional filepath from which the source was read

This function throws ParserException if parsing fails.

### Template parseFile(std::string filepath)

**Brief:** parse a template

Parameters:
- filepath of the template to parse

This function uses `parse()` internally.

