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

A blob is generally defined using the following pattern:

` (name|value|type|visibility) `

- **name**: The identifier for the blob.
- **value**: The data or expression contained in the blob. If arguments of a blob which is in this value aren't set, they are passed as arguments by the entire blob, based on the order in code.
- **type**: The type of the blob, also in form of a blob. Can be omitted when type can be inferred by the value.
- **visibility**: The visibility when its file is imported using the import() blob. Defaults to private().

When a blob is defined another time with the same name, the old definition is overwritten.

## Blob Invocation

Blobs can be invoked using:

` name(parameters seperated by space) `

- If there are no parameters, the parentheses can be omitted.

## Standard Library

As blobs can only be created out of other blobs, here is a standard library for Blobble:

- **int**: Integer type
- **intOf()**: Integer type creation with digits
- **toInt(float)**: Float to integer (decimal places get cut)
- **float**: Float type
- **floatOf()**: Float type creation with digits and decimal point
- **toFloat(int)**: Integer to float
- **add(float float)**: Add two floats together
- **char**: Character type
- **charOf()**: Character type creation with letters
- **str**: String type
- **strOf()**: String type creation with letters
- **toStr(null)**: Create a string out of any other type
- **bool**: Boolean type
- **boolOf()**: Boolean type creation (` true `/` false`)
- **list(type)**: List type
- **listOf()**: List type creation with as many arguments as you want
- **listElement(list int)**: Get the element at the specified position
- **null**: Null type / Null type creation 
- **if(bool null)**: If-Statement, the null blob only gets executed when bool is ` true `
- **while(bool null)**: While-Statement, the null blob gets executed as long as bool is ` true `
- **for(list null(index))**: For-Statement, the null blob gets executed for each iteration of the list with the index
- **log(str)**: Log a String to the standard output
- **comment()**: Comment with letters
- **intra**: When set as visibility, the blob will not be imported
- **inter**: When set as visibility, the blob will be imported
- **import(string)**: Import all inter-visible blobs from a specified file (relative path)

## Examples

Here's a quick overview of how to use Blobble:

```blobble
// Define a string blob
(greeting|str(Hello, Blobble!))

// Log the greeting
(logGreeting|log(greeting))

// Define an integer blob
(number|int(42))

// Define a function to double a value
(doubleValue|mul(int(2))) // Doubles the input

// Calculate the doubled value of 42
(doubled|doubleValue(number)) 

// Log the results
(logDoubled|log(doubled))

// Execute logging
logGreeting()  // Outputs: "Hello, Blobble!"
logDoubled()   // Outputs: "84"
```

## Contributing

pls help me with the concept ive got no idea what im doing :3

## License

This project is licensed under the Apache 2.0 License. See the LICENSE file for more details.


