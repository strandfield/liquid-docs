---
layout: default
title: "Value class"
parent: "Class reference"
---

# Value Class

**Brief:** holds a value that can be used by the renderer

## Detailed description

## Members documentation

### Value()

**Brief:** constructs a null value

### Value(nullptr_t)

**Brief:** constructs a null value

### Value(bool b)

**Brief:** constructs a boolean value

### Value(int n)

**Brief:** constructs an integer value

### Value(double x)

**Brief:** constructs a real value

### Value(std::string str)

**Brief:** constructs a string value

### Value(const char* str)

**Brief:** constructs a string value

### Value(std::vector\<Value> vals)

**Brief:** constructs an array of values

### Value(std::map\<std::string, Value> dict)

**Brief:** constructs a map of values

### Value(std::shared_ptr\<IValue> impl)

**Brief:** constructs a value from an implementation

### bool isNull() const

**Brief:** returns whether the value is null

### bool isArray() const

**Brief:** returns whether the value is an array

A value for which `isArray()` returns true can be converted to an Array using `toArray()`.

### bool isMap() const

**Brief:** returns whether the value is a map

A value for which `isMap()` returns true can be converted to a Map using `toMap()`.

### bool isSimple() const

**Brief:** returns whether the value is simple

A value is simple if it is neither an array, a map, or null.

You can test the type of the value using `is<T>()` and retrieve it using `as<T>()`.

### Array toArray() const

**Brief:** attempts a conversion to an array

If the value is not an array, an empty array is returned.

### Map toMap() const

**Brief:** attempts a conversion to a map

If the value is not a map, an empty map is returned.

### std::type_index typeIndex() const

**Brief:** returns the type_index of the C++ value

This is the type of the pointer returned by `data()`.

### void* data() const

**Brief:** returns a pointer to the C++ value stored in this object

The type of the C++ value can be retrieved using `typeIndex()` and or tested with `is<T>()`.

### size_t length() const

**Brief:** returns the length of the array represented by this value

If this value is not an array, this returns 0.

### Value at(size_t index) const

**Brief:** access the array by index

If this value is not an array, this returns a null Value.

### std::set\<std::string> propertyNames() const

**Brief:** returns the keys of a map value

If this value is not a map, this returns an empty set.

Note that depending on how the map is implemented, this set can be smaller than the actual set of proprety names. For example, an object that provides a 'parent' property may choose not to report it in propertyNames() as iterating recursively would produce an infinite loop.

### Value property(const std::string& name) const

**Brief:** retrieves the property of a map

If the map does not contain a property with the given name, a null value is returned.

### const std::shared_ptr\<IValue>& impl() const

**Brief:** returns a pointer to the implementation

