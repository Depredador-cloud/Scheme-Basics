# Scheme-Basics

# Scheme Programming Guide

Welcome to the Scheme Programming Guide! This guide aims to provide a comprehensive introduction to Scheme, a minimalist, multi-paradigm programming language.

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Basic Syntax](#basic-syntax)
4. [Control Structures](#control-structures)
5. [Procedures](#procedures)
6. [Recursion](#recursion)
7. [Advanced Topics](#advanced-topics)
   - [Data Abstraction](#data-abstraction)
   - [Vectors](#vectors)
   - [Object-Oriented Programming](#object-oriented-programming)
   - [Continuations](#continuations)

## Introduction

Scheme is a functional programming language and a dialect of Lisp. It is known for its simple and clean syntax, making it a great choice for beginners and advanced programmers alike. Scheme emphasizes recursive algorithms and symbolic computation.

## Getting Started

### Interacting with Scheme

To start using Scheme, you need to install an interpreter. Some popular interpreters include:
- **Racket**: A modern programming language in the Lisp-Scheme family.
- **Chez Scheme**: A fast and efficient interpreter.

You can start the interpreter by typing `scheme` or `racket` in your terminal.

### Simple Expressions

Scheme uses prefix notation for expressions. For example, to add two numbers, you write:

```scheme
(+ 1 2)
```

This will return `3`.

## Basic Syntax

### Variables and Let Expressions

Variables in Scheme are defined using the `define` keyword:

```scheme
(define x 10)
```

For local bindings, `let` expressions are used:

```scheme
(let ((x 5)
      (y 10))
  (+ x y))
```

### Lambda Expressions

Lambda expressions are used to create anonymous functions:

```scheme
(lambda (x) (+ x 1))
```

### Top-Level Definitions

Top-level definitions allow you to define functions and variables globally:

```scheme
(define (square x)
  (* x x))
```

### Conditional Expressions

Conditional expressions are written using `if`:

```scheme
(if (> x 0)
    'positive
    'non-positive)
```

## Control Structures

### Sequencing

Sequencing is done using the `begin` keyword:

```scheme
(begin
  (display "Hello, ")
  (display "world!"))
```

### Conditionals

Scheme provides several conditional forms, including `cond`:

```scheme
(cond
  ((> x 0) 'positive)
  ((< x 0) 'negative)
  (else 'zero))
```

### Recursion and Iteration

Recursion is a fundamental concept in Scheme:

```scheme
(define (factorial n)
  (if (= n 0)
      1
      (* n (factorial (- n 1)))))
```

### Delayed Evaluation

Delayed evaluation can be achieved using `delay` and `force`:

```scheme
(define delayed-value (delay (+ 1 2)))
(force delayed-value)
```

## Procedures

### Defining Procedures

Procedures are defined using the `define` keyword:

```scheme
(define (add x y)
  (+ x y))
```

### Higher-Order Procedures

Scheme supports higher-order procedures, which take other procedures as arguments or return them as results:

```scheme
(define (apply-twice f x)
  (f (f x)))

(apply-twice square 2)  ; Returns 16
```

## Recursion

### Simple Recursion

Recursion is used extensively in Scheme for iteration and looping:

```scheme
(define (sum n)
  (if (= n 0)
      0
      (+ n (sum (- n 1)))))
```

### More Recursion

More complex recursive patterns can be achieved, such as tree recursion:

```scheme
(define (fib n)
  (if (< n 2)
      n
      (+ (fib (- n 1)) (fib (- n 2)))))
```

## Advanced Topics

### Data Abstraction

Scheme supports various forms of data abstraction, such as lists and pairs:

```scheme
(define pair (cons 1 2))
(car pair)  ; Returns 1
(cdr pair)  ; Returns 2
```

### Vectors

Vectors are a fixed-size, mutable sequence type:

```scheme
(define vec (vector 1 2 3))
(vector-ref vec 1)  ; Returns 2
```

### Object-Oriented Programming

Scheme supports object-oriented programming through closures and message-passing style:

```scheme
(define (make-counter)
  (let ((count 0))
    (lambda (msg)
      (cond ((eq? msg 'inc) (set! count (+ count 1)))
            ((eq? msg 'dec) (set! count (- count 1)))
            ((eq? msg 'get) count)))))
```

### Continuations

Continuations represent the state of the program at a certain point and can be used for advanced flow control:

```scheme
(call/cc (lambda (k) (k 42)))  ; Returns 42
```

---

This guide provides a foundation for Scheme programming. For more detailed examples and advanced topics, refer to the provided resources:

- [The Scheme Programming Language, 3rd Edition](#)
- [Scheme and the Art of Programming](#)

Happy coding!
