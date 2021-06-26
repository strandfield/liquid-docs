---
layout: default
title: "Renderer class"
parent: "Class reference"
---

# Renderer Class

**Brief:** base class for renderers

## Detailed description

## Members documentation

### Renderer()

**Brief:** constructs a renderer

### ~Renderer()

**Brief:** destroy the renderer

### void reset()

**Brief:** resets the renderer

### Context& context()

**Brief:** returns the renderer context

### std::map\<std::string, Template>& templates()

**Brief:** returns the renderer built-in templates

These templates can be used with an 'include' tag.

### const std::map\<std::string, Template>& templates() const

**Brief:** returns the renderer built-in templates

### const std::vector\<Renderer::Error>& errors() const

**Brief:** returns the errors generated during the last call rendering

### const Template& model() const

**Brief:** returns the template that is currently used

This function can only be called during rendering, i.e. inside a call of `render()`.

### std::string render(const Template& t, const liquid::Map& data)

**Brief:** renders a template using the given data

Parameters:
- the input template
- the input data

This function first resets the renderer.

Any error generated during rendering is written in the output. You can check programmatically if any error occured with a call to `errors()`.

