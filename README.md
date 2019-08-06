# Things About Ruby

This document is an introduction to the practical use of
Ruby.

It is aimed at people who already know how to program in
other languages.

## History

Ruby was invented by Yukihiro Matsumoto. He started working
on it in 1993. The first version was released in 1995.

## Philosophy

Ruby is an object-oriented scripting language.

In Ruby, everything is an object.
- okay, well, syntactic structures aren't.
- but everything that can be referred to at runtime is.

A hallmark of OO languages is that all computation is
modeled as messages sent from one object to another.

You may be familiar with this idea being modeled with
method-calling syntax. `person.name()` sends a message
`name()` to the object referenced by the variable `person`.

But ruby uses the same message-sending idea for other
constructs as well:

For example, the Ruby code `1 + 2` sends a message `+` to
the object `1` with `2` as an argument. Craziness!

Similarly, the comparison `true == false` sends a message
`==` to the object `true` with the argument `false`.

This fact about Ruby means you can overload operator
messages like `+` and `==` on your own classes to define
objects with particular semantics.

## Doing a Thing

Here's how you tell `ruby` to run a file, from the command
line:

```
ruby path/to/my_code.rb
```

Let's do a "hello world" example:

```bash
echo 'puts "Hello, world!"' > hello.rb
ruby hello.rb
```

`puts` is short for "put string" and is the normal way of
printing things in Ruby. The name comes from C. The standard
ruby interpreter (MRI, or Matz's Ruby Interpreter) is
written in C, and a lot of its lower-level constructs are
C-inspired.

## Interpretation

Ruby code is evaluated dynamically. There is no compiler.

There is no spec for Ruby syntax. The parser is the only
spec. Even the guy who wrote the parser (Matz) doesn't
remember exactly how it works.

When a ruby file is loaded by the interpreter, the file is
first parsed. If it's not valid Ruby, a syntax error is
thrown.

There is a single global namespace. There is no way to scope
classes, variables, etc. to a file.


## Syntax

Ruby has classes:

```
class Elephant
  # ...
end
```

Classes have instances:

```
an_elephant = Elephant.new
```

## Style

Variables and methods are `snake_case`.

Classes and modules are `CamelCase`.

Constants are `YELLING_CASE`.

Identifiers that start with a capital letter are constants.
Ruby won't let you reassign them. However, you can still
modify the objects they point to.

Boolean methods end with a question mark: `success?`
