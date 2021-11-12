# Haskell 101

## Introduction

_A `general-purpose, statically typed, purely functional, lazy evaluated` programming language, that will hurt you more than **your first breakup(no exaggeration).**_

**_A language that will make you feel like a noob, doesn't matter how many years of experience you have writing lame `JAVA` code._**

Born out of the complexities of [Lambda Calculus](https://en.wikipedia.org/wiki/Lambda_calculus) and [Category Theory](https://en.wikipedia.org/wiki/Category_theory), in the dark valleys of [Glasgow](https://en.wikipedia.org/wiki/Glasgow_Haskell_Compiler), `Haskell` nerds will make sure you leave that book after the preface and never come back because you realize, you are too dumb for this shit.

**A language so gorgeour, you will fall in love. A language so powerful, it will make your brain bigger(like physically bigger). A language so sick, even I don't understand half of it(but the other half, that's some kick ass stuff).**

## `Step[0]`

If you plan to try some of the examples, I would highly recommend setting up `Haskell` locally on your machine. You can follow [this](https://www.haskell.org/platform/) guide to download and setup `ghc` and `ghci`, we will using `ghci` for all examples.

**`Can't I just using an online compiler ??`**

Well, in theory sure, if you google, you can find some options, I have used [haskell replit](https://replit.com/languages/haskell) in the past, **_but_**(and "a big fat `but`, as far as `but's` go") there is a problem, you see currently you are a `Haskell` baby, all you know is and do is cry, but these `REPL` environments are designed for grownups. And if I were to take you from a baby to grownup, we will have to talk about, what `purely functional` really means, and how all `IO` is always impure by design and then I will have to tell you about how `Haskell` ended up going around that issue using the explict `IO Monad`, but then you will ask what a `Monad` is, and then I will say, "whatever you want it to be" while simultaneously being something "no one really understands, we all just pretent" and then we will have to talk about "that thing" and then "that other thing" and after a while, we reach stuff, even I don't understand and by then you will have a serious headache and man oh man, a serious headache can cause permanent brain damage to a baby, so no I ain't taking that risk, just setup the f\*\*king thing on your machine locally.

## A quick overview

### `Haskell` is `general-purpose`

Can be used to build applications of all sort, there is no specific domain which the language was designed for. `DSLs`(Domain Specific Languages) like `SQL` are examples of some languages which were designed to only solve problems of a smaller, restrictive use-case, but there is nothing like that in `Haskell`.

Also randomly, `--` in `Haskell` is single line comment, while `{--}` create multiline comments.

```haskell
-- This is a single line comment

{-
I am
multiline comment
-}
```

### `Haskell` is `purely functional`

which implies functions can't have [side effect](<https://en.wikipedia.org/wiki/Side_effect_(computer_science)>), or think of them as more like functions in `Mathematics`, they take an input and produce an output. You can apply rules which govern what can be a possible input and what can be a possible output, just like in `maths` refering to the `Domain` and `Range` of a function, and for any given input, the function will product the exact same output **_always_**.

There are no `classes`, `objects`, `references`, `pointers`, `mutable-variables`, none of that and so almost all you know as an `OOPS` [btch](./definations.md#foo) goes out of the windom.

The function syntax in `Haskell` is very easy, lets see a few examples

```haskell
-- Function called `addTwoNumbers` takes two numbers and returns the result of addition.
addTwoNumbers a b = a + b

-- Function called `multiplyTwoNumbers` takes two numbers and returns the result of multiplication.
multiplyTwoNumbers a b = a * b
```

Hope that gave you a bit of intutition, I know it wasn't much but I don't think this can be taught in a flyby overview writeup, so I recommend reading [here](http://learnyouahaskell.com/syntax-in-functions).

### `Haskell` is `statically typed`

You can specify types for things in `Haskell`, but its kinds optional, till you have that case where it isn't, but very rare to have that case. This optional behaviour is thanks to `Haskells type inference` system, which is **chef's kiss**.

lets look at some exmaples

```haskell
-- You can add types to constants
intTypeValuesOnly :: Int
intTypeValuesOnly = 10    -- (ok)
intTypeValuesOnly = 6.212 -- (bad, gives error, see image below)

-- You can add types to functions
addTwoInts :: Int -> Int -> Int
addTwoInts a b = a + b

addTwoInts 10 20  -- 30
addTwoInts 5.2 10 -- error similar to example above.
```

![results of the above code execution in ghci](./error_one.png)

Hope that all was pretty straigh forward, if you wanna learn more about the available types, you can read at [http://learnyouahaskell.com/types-and-typeclasses](http://learnyouahaskell.com/types-and-typeclasses)

### `Haskell` has `lazy evaluation`

This one is interesting and a key differenciating factor between `Haskell` and some of the other functional programming languages. Lazy evaluation basically means, `Haskell` won't execute some code, untill it needs to use its output, say for printing it to the stdout or something.
