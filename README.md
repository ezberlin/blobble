# Blobble

> "Simplicity is the ultimate sophistication." – Leonardo da Vinci

Blobble is a simple yet powerful programming language designed for flexibility and ease of use. In Blobble, everything is a blob, allowing you to define and manipulate data structures effortlessly.

## Table of Contents

1. [Overview](#overview)
2. [Blob Definition](#blob-definition)
3. [Blob Invocation](#blob-invocation)
4. [Examples](#examples)
5. [Contributing](#contributing)
6. [License](#license)

## Overview

Blobble operates on the principle that every piece of data can be encapsulated in a "blob." This makes it easy to create reusable components and manage data flow within your programs.

## Blob Definition

A blob can exist in the main file or inside of another blob is generally defined using the following pattern:

` (name|value|type|visibility|sugar) `

- **name**: The identifier for the blob.
- **value**: The data or expression contained in the blob. If arguments of a blob which is in this value aren't set, they are passed as arguments by the entire blob, based on the order in code.
- **type**: The type of the blob, also in form of a blob. Can be omitted when type can be inferred by the value.
- **visibility**: The visibility when its file is imported using the import() blob. Defaults to private().
- **sugar**: An optional way to make your blobs with one or two parameters more concise by putting a non-alphanumeric character as an operator in front or between the parameter(s).

When a blob is defined another time with the same name, the old definition is overwritten.

## Blob Invocation

Blobs can be invoked using:

` name(parameters seperated by space) `

- If there are no parameters, the parentheses can be omitted.

## Standard Library

As blobs can only be created out of other blobs, here is a standard library for Blobble:

### Types

- **int**: Integer type
- **intOf(|^)**: Integer type creation with digits
- **toInt(float)**: Float to integer (decimal places get cut)
  
- **float**: Float type
- **floatOf(|~)**: Float type creation with digits and decimal point
- **toFloat(int)**: Integer to float
  
- **char**: Character type
- **charOf(|')**: Character type creation with letters
  
- **str**: String type
- **strOf(|@)**: String type creation with letters
- **toStr(null)**: Create a string out of any other type
- **embedOf(null|:)**: The contents of this function can be directly embedded into a string
- **strOf(|@)**: String type creation with letters
  
- **bool**: Boolean type
- **boolOf(|?)**: Boolean type creation (` true `/` false`)
  
- **list(type)**: List type
- **listOf()**: List type creation with as many arguments as you want
- **listElement(list int)**: Get the element at the specified position

- **type(type)**: Type type, consists of multiple blob definitions and inherits from the parameter type
- **getProperties(null null|,)**: Get the value of properties with inter or extra visibility of a blob
  
- **null**: Null type / Null type creation 

### Control Structures

- **if(bool null)**: If-Statement, the null blob only gets executed when bool is ` true `
- **while(bool null)**: While-Statement, the null blob gets executed as long as bool is ` true `
- **for(list null(index))**: For-Statement, the null blob gets executed for each iteration of the list with the index

### Math & Logic

- **add(number number|+)**: Add two numbers together
- **sub(number number|-)**: Subtract two numbers together
- **mul(number number|*)**: Multiply two numbers together
- **div(number number|/)**: Divide two numbers together
- **mod(number number|%)**: Take the modulo of the numbers


- **eq(null null|=)**: Check if two numbers are equal
- **smaller(number number|<)**: Check if the first number is smaller than the second
- **larger(number number|>)**: Check if the first number is larger than the second

- **not(bool|!)**: Invert a boolean
- **and(bool bool|&)**: Logical And
- **or(bool bool|")**: Logical Or

### Importing & Visibility

- **intra**: When set as visibility, the blob will not be imported and not visible outside of objects
- **inter**: When set as visibility, the blob will not be imported but visible outside of objects
- **extra**: When set as visibility, the blob will be imported and visible outside of objects
- **import(string)**: Import all inter-visible blobs from a specified file (relative path)

### Programming Utilities

- **get(str)**: Log a String to the standard output and get a string as a response
- **log(str)**: Log a String to the standard output
- **comment(|#)**: Comment with letters

## Examples

Here's a quick overview of how to use Blobble:

```blobble
# Define a string blob
(greeting|@(Hello, Blobble!))

# Log the greeting in an embedded string
(logGreeting|log(@(My greeting is :greeting!)))

# Define an integer blob
(integer|^42)

# Define a function to add 10 to a value
(addTen|add(^10))

# Calculate 42 plus 10
(added|addTen(integer)) 

# Log the results
(logAdded|log(added))

# Recursive Fibonacci Function
(fib|
    (n|intOf())
    if(n=^0) ^0
    if(n=^1) ^1
    fib(n-^1)+fib(n-^2)
)

# OOP-Blobs with type
(pair|(first||null) (second||null) (contents|@(The Pair contains :first and :second)||inter)|type(null))
(myPair|pair(1 2))
log(myPair,contents)

# Execute logging
logGreeting()              # Outputs: "Hello, Blobble!"
if(integer>^50 logAdded()) # Outputs: 52
log(fib(10))               # Outputs: 34

```

## Contributing

pls help me with the concept I've got no idea what im doin :3

## License

This project is licensed under the Apache 2.0 License. See the LICENSE file for more details.
