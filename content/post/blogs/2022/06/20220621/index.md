+++
author = "Matthew Kwan"
title = "Software Translation"
date = "2020-06-25"
description = "How software even works (and my dismay for learning it so late)"
categories = [
    "blogs",
    "software",
]
image = "sloth.webp"
+++

## Introduction
Hello again :smile:, welcome back to this blog. Today, we have a very fun topic that I randomly learned when trying to pick up more Go. The quick topic for today is software translation, and a high level overview of how what we code actually turns into something that our computers can process.

## Different Types of Languages
There are three main different types of languages that are used:

- Machine Language
- Assemby Language
- Higher Order Language

### Machine Language
Machine language is the elemental language that is read by all computers. This is what is read by a CPU, and is composed of digital binary numbers, which is essentially zeros and ones. Ultimately, this is the only language that CPUs are able to read, and how a CPU reads it varies between the different types of processors. An easy example of this would be typical Intel processors versus the new native Apple M(x) chips.

I won't go too deep into instructions, but for an 8 bit (binary digit) operation, meaning that the instruction is comprised of 8 zeroes and ones combined, the first four bits would tell the CPU what to do, and the last four would be the data to use.

### Assembly Language
The Assembly language, often refered to as Assembly, is a derivative of Machine Language that includes in semantics to make it slightly more readable by humans. The goal here is to make it more interpretable.

### Higher Order Language
This is what everyone is mostly familiar with. These are standard programming languages that developers use to code in to create functionality. Examples of these are Python, Java and Go. These utilize functions, modules, objects and etc to create the functionality that a developer needs. 

Ultimately, the code from these languages can not be sent directly to the CPU for processing, as it is not Machine Language. As such, something needs to be done in order for this code to be properly processed, leading in to the next section of this post.

## Compilers and Interpreters
So we know that higher order languages must be somehow converted into Machine Language in order for the CPU to process it. There are two main methods of doing so, and which of these a language uses has heavy implications of the performance of the language.

### Compiler
One possibility is for a program to be written, and then _compiled_ into a binary that is written in Machine Language. This is nice as you end up with a binary that is easily executable at the end of compilation. Some examples of compiled languages are Go, C++, and Java (kinda). 

### Interpreter 
Another option is to have an interpreter. What this does is it interprets the higher order code during execution on the fly to Machine Language for the CPU to read. Naturally this requires an interpreter. An example of an interpreted language is Python. 

### Tradeoffs
As you may expect, compiled languages usually perform much faster at runtime as they are already in a state that is ready to be read by the CPU. They don't need to incur any extra processing time to translate the code into Machine Language at runtime. However, interpreters tend to come with a bunch of features that make life easier. They have the ability to infer variable types at runtime (like in Python), and they can manage the memory of the program during execution automatically. This enables different features like garbage collection.

> ### Go Propaganda
> For some context, I learned the majority of this during a Golang course I found on Coursera, and the reason this was shared was to reveal how cool Go is. It is a compiled language, meaning that you are still compiling Machine Language binaries before runtime, yet it has some cool features that normally only interpreted languages would have, namely garbage collection.
