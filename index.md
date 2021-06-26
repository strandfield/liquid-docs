---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: Home
layout: home
nav_order: 0
---

[![Build Status](https://api.travis-ci.org/bandicode/liquid.svg?branch=master)](https://travis-ci.org/bandicode/liquid)
[![codecov](https://codecov.io/gh/bandicode/liquid/branch/master/graph/badge.svg)](https://codecov.io/gh/bandicode/liquid)

This project is a C++ port of [Shopify's Liquid template engine](https://github.com/Shopify/liquid) (originally written in Ruby).

```cpp
std::string str = "Hello {% raw %}{{{% endraw %} name }}!";

liquid::Template tmplt = liquid::parse(str);

liquid::Map data;
data["name"] = "Alice";
std::string result = tmplt.render(data)
  
assert(result == "Hello Alice!");
```

## Features

Supported tags include:
- `if`, `elsif` and `else`
- `for`
- `break` and `continue`
- `assign`

The default template engine does not provide any filters, but custom filters can easily be implemented by subclassing the `Renderer` class (see `tests.cpp`).
