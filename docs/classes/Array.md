---
layout: default
title: "Array class"
parent: "Class reference"
---

# Array Class

**Brief:** provides an array of value

## Detailed description

## Members documentation

### Array()

**Brief:** constructs an empty array

### Array(std::vector\<Value> vals)

**Brief:** constructs an array from a list of values

### Array(std::shared_ptr\<IValue> impl)

**Brief:** constructs an array from its implementation

### size_t length() const

**Brief:** returns the length of the array

### Value at(size_t index) const

**Brief:** retrieves an element by index

Parameters:
- index

### bool isWritable() const

**Brief:** returns whether an array is writable

You can call `push()` on a writable array to add elements to it.

Arrays constructed using the default constructor, or the vector constructor of this class are writable.

### void push(Value val)

**Brief:** adds a value to the array

The array must be writable.

### Value& operator\[](size_t index)

**Brief:** access an element by index

Note that unlike `at()`, this function returns a modifiable reference to the element.

###  operator Value() const

**Brief:** converts the array to a value

### const std::shared_ptr\<IValue>& impl() const

**Brief:** returns a pointer to the implementation

