# WORK IN PROGRESS

# Haskell 101

## Introduction

_A `general-purpose, statically typed, pure functional, lazy evaluated` programming language, that will hurt you more than **your first breakup(no exaggeration).**_

**_A language that will make you feel like a noob, doesn't matter how many years of experience you have writing lame `JAVA` code._**

Born out of the complexities of [Lambda Calculus](https://en.wikipedia.org/wiki/Lambda_calculus) and [Category Theory](https://en.wikipedia.org/wiki/Category_theory), in the dark valleys of [Glasgow](https://en.wikipedia.org/wiki/Glasgow_Haskell_Compiler), `Haskell` nerds will make sure you leave that book after the preface and fucking scared to never come back, making you realize, you are too dumb for this shit.

**A language so gorgeour, you will fall in love. A language so powerful, it will make your brain bigger(like physically bigger). A language so sick, even I don't understand half of it(but the other half, that's some kick ass stuff).**

<br />

## Let's learn the half I understand

`Haskell` is a purely functional language, which is a just a fancy way of saying, no classes, no objects, functions can be passed around just like data.

Here is an example,

```haskell
findMax :: (Num a) => (a -> a -> a) -> a -> a -> a
findMax f a b = f a b
```

![Result](./example_one.png)

There is a lot going on in this example, and you will learn all these things as we go along, but for now just focus on the last line. We have a function called `findMax`, which takes a function `f` as its argument, which demonstrates the behavious.

`findMax max 10 20` used the inbuild function called `max` to find the bigger number of two passed as arguments.

Functions like `findMax` are sometimes also refered to as `Higher Order Functions`, which just means a function that either takes another function as argument or returns a function as its result, and if you are coming to this article with experience in one of the modern programming languages like `Javascript`, `Python`, etc, you have already seem functions accepting other functions as arguments, think of your `map`, `filter`, `reduce`, although functions returing other functions is a rare sight. But in `Haskell`, functions return other functions all the time and is a very important aspect of the language.

<br />

### Your first program, or two 😛😛

If you don't have the `Haskell` compiler installed already, I would recommend using the [Online Haskell REPL](https://replit.com/languages/haskell).

When you open the repl, you are greeted with the mandatory `helloworld` example, which is just printing the string using the inbuilt `putStrLn`.

`main = putStrLn "Hello, World!"` print "Hello, World!" to the screen.

Let's move on and define some variables, **Oppsie**, `Haskell` doesn't have those, happy to disappoint. `Haskell` doesn't have variables because all values are immutable, so you can't change any value once assign it to a name. There are some other nerdy details here, but we can ignore those.
