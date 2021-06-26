---
layout: default
title: "IValue class"
parent: "Class reference"
---

# IValue Class

**Brief:** provides an interface for the Value class

## Detailed description

You can derive from this class to expose your C++ type to the Renderer class without manually constructing them using Map and Array.

There are typically two scenarios.

If you have a C++ object, you can expose it to the renderer by storing it in an IValue and overriding `is_map()`, `propertyNames()` and `property()`.

If you have a list of C++ objects, you can expose it ot the renderer by storing it in an IValue and overriding `is_array()`, `length()` and `at()`.

In both cases, you will also need to override `type_index()` and `data()`. This will allow you to retrieve your C++ object with `Value::as<T>()`.

## Members documentation

### virtual std::type_index type_index() const = 0

**Brief:** returns the type_index of the data

### virtual ~IValue()

### virtual bool is_null() const

**Brief:** returns whether this is the null value

The default implementation returns false.

### virtual bool is_array() const

**Brief:** returns whether this value is an array

The default implementation returns false.

### virtual bool is_map() const

**Brief:** returns whether this value is a map

The default implementation returns false.

### virtual void* data()

**Brief:** returns a pointer to the C++ variable this object exposes

The default implementation returns nullptr.

You should override `type_index()` to return the type_index of the variable.

### virtual size_t length() const

**Brief:** returns the length of an array.

The default implementation returns 0.

If `is_array()` returns false, this function should return 0.

### virtual Value at(size_t index) const

**Brief:** access an array by index

The default implementation returns a null value.

If `is_array()` returns false, this function should return a null value.

### virtual std::set\<std::string> propertyNames() const

**Brief:** returns the names of the property in a map

The default implementation returns an empty set.

If `is_map()` returns false, this function should return an empty set.

This function is not required to return an exhaustive list. For example, if an IValue exposes an object that has some computed properties, or properties that would induce a cycle (e.g. 'parent' and 'children'), it is recommended not to list them in this function.

### virtual Value property(const std::string& name) const

**Brief:** the name of the property

The default implementation returns a null value.

If `is_map()` returns false, this function should return a null value.

