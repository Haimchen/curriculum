# Getting Started

## Goals

  - Learn how to use the Elm REPL
  - Learn how to manipulate strings and numbers in Elm
  - Learn how to call functions
  - Learn where to find documentation about the Elm core library

## Steps

### <input type="checkbox"> Step 1

Start the Elm REPL ([What is a REPL?](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)) from your terminal:

```bash
elm-repl
```

You should see the following message:

```
---- elm-repl 0.17.1 -----------------------------------------------------------
 :help for help, :exit to exit, more at <https://github.com/elm-lang/elm-repl>
--------------------------------------------------------------------------------
>
```

### <input type="checkbox"> Step 2

Now that you are in the REPL, you can write your first Elm code! Code you should try out in the REPL is written on lines starting with `>`.

You can enter values, and Elm will tell you the type of the values.  Try typing
strings, numbers, and simple mathematical expressions:

```
> "Hello"
"Hello" : String
> 100
100 : number
> 100.5
100.5 : Float
> 50 / 7
7.142857142857143 : Float
> 4 + 3 * (6 - 2)
16 : number
```

### <input type="checkbox"> Step 3

You can define and refer to variables:

```
> x = 5
5 : number
> y = 3
3 : number
> x + y
8 : number
```

### <input type="checkbox"> Step 4

You can concatenate strings using the `++` operator:


```
> "Hello" ++ ", World"
"Hello, World" : String
> name = "Anna"
"Anna" : String
> "Hello, " ++ name ++ "!"
"Hello, Anna!" : String
```

### <input type="checkbox"> Step 5

If you try to perform operations that don't make sense, Elm will try to tell you
what's wrong:

```
> 10 + "Betsy"
-- TYPE MISMATCH --------------------------------------------- repl-temp-000.elm

The right argument of (+) is causing a type mismatch.

3|   10 + "Betsy"
          ^^^^^^^
(+) is expecting the right argument to be a:

    number

But the right argument is:

    String

Hint: To append strings in Elm, you need to use the (++) operator, not (+).
<http://package.elm-lang.org/packages/elm-lang/core/latest/Basics#++>

Hint: I always figure out the type of the left argument first and if it is
acceptable on its own, I assume it is "correct" in subsequent checks. So the
problem may actually be in how the left and right arguments interact.
```

### <input type="checkbox"> Step 6

To call a function in Elm,

Here are some of the functions that are always available in Elm: `toString`, `max`, `min`, `sqrt`, `round`, `floor`.  You can find more about these and other functions in the [`Basics` module documentation](http://package.elm-lang.org/packages/elm-lang/core/latest/Basics)

```
> toString 10 ++ "!"
"10!" : String
> min 9 1
1 : number
```

To disambiguate order of operations, use parentheses.

```
> round (96 / 7)
14 : Int
```

### <input type="checkbox"> Step 7

Let's use some functions from the String module:


```
> import String
> String.toUpper "Carey"
"CAREY" : String
> String.split "," "Apple,Apricot,Avocado,Banana,Blackbery"
["Apple","Apricot","Avocado","Banana","Blackbery"] : List String
> String.join " -- " (String.split "," "Apple,Apricot,Avocado")
"Apple -- Apricot -- Avocado" : String
```

### <input type="checkbox"> Step 8

Now let's define and use our own functions.

When Elm shows the type of a functions, it uses arrows `->`.  The rightmost type is the return value, and the other types are the parameters to the function.  For example, `Int -> String -> Float` is the type of a function that takes two parameters: the first is an Int, the second is a String, and the function returns a Float.

```
> f x = x * 3
<function> : number -> number
> f 10
30 : number
> f
<function> : number -> number
> add a b = a + b
<function> : number -> number -> number
> add 10 4
14 : number
> sayHello name = "Hello, " ++ name
<function> : String -> String
> sayHello "Janice"
"Hello, Janice" : String
```

### Step ...

Exit the Elm REPL by typing `:exit`, or `CTRL-C` (`CMD-C` on Mac).

> add
<function> : number -> number -> number
> add 10
<function> : number -> number
> addTen = add 10
<function> : number -> number
> addTen 5
15 : number
> addTen 24
34 : number


Practical Goals: Students should be able to load the repl and do basic transformations.
Learning Goals: Students should start mapping elm to languages they know.
Structure of in-person lesson: Teacher should walk through the lessons alongside students, live coding in the repl.
Structure of written lesson:
How to use the repl (with explicit instructions on how to close it)
Section on strings (with explanation of repl output)
Defining literal strings
String concatenation with ++
Calling functions, like String.toUpper, String.split
Section on numbers with addition as an example
Section basic functions (perhaps an add2 function)
end with defining sayHello name = "Hello, " ++ name (this is the same as the first example in the next part of the curriculum)