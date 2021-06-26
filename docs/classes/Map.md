---
layout: default
title: "Map class"
parent: "Class reference"
---

# Map Class

**Brief:** provides a key/value container

## Detailed description

## Members documentation

### Map()

**Brief:** constructs an empty map

### Map(std::map\<std::string, Value> dict)

**Brief:** constructs a map from given values

### Map(std::initializer_list\<std::pair\<const std::string, Value\>>&& pairs)

**Brief:** constructs a map from given values

### Map(std::shared_ptr\<IValue> impl)

**Brief:** constructs a map from its implementation

### std::set\<std::string> propertyNames() const

**Brief:** returns the keys of a map value

### Value property(const std::string& name) const

**Brief:** retrieves a property by name

Parameters:
- property name

### bool isWritable() const

**Brief:** returns whether the map is writable

### void insert(const std::string& name, Value val)

**Brief:** inserts a new value into the map

Parameters:
- property name
- property value

The map must be writable.

### Value& operator\[](const std::string& name)

**Brief:** access a property by name

Parameters:
- property name

Unlike `property()`, this function returns a modifiable reference to the value.

###  operator Value() const

**Brief:** converts the map to a value

### const std::shared_ptr\<IValue>& impl() const

**Brief:** returns a pointer to the implementation

