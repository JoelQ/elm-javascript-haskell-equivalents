# Functional Syntax in JS, Elm, and Haskell

Elm developers often come from one of two opposite directions.

1. JavaScript programmers who know front-end web dev but want to introduce typed FP
2. Haskell programmers who know typed FP but want to use it for front-end web dev

This leads to lots of comparisons of Elm functions to similar ones in both
JavaScript and Haskell. Now you can have all of them in one place.

## Collections

Collection data structures are core to most of programming. Here's how the
various collections in Elm compare to equivalents in JavaScript and Haskell.

| Purpose                                 | JavaScript | Elm     | Haskell |
|-----------------------------------------|------------|---------|---------|
| Random access via key - dynamic keys    | Object     | Dict    | Map     |
| Random access via key - static keys     | N/A        | records | records |
| Unique values                           | Set        | Set     | Set     |
| Preserve order, random access via index | Array      | Array   | Array   |
| Preserve order, no random access        | N/A        | List    | List    |

## List transformations

The default collection in Elm is the list. This is a breakdown of some of the
more common functional list operations.

| Purpose                               | JavaScript               | Elm           | Haskell  |
|---------------------------------------|--------------------------|---------------|----------|
| Combine all elements into a new value | `Array.prototype.reduce` | `List.foldl`  | `foldl`  |
| Apply a function to each element      | `Array.prototype.map`    | `List.map`    | `fmap`   |
| Only keep elements that match         | `Array.prototype.filter` | `List.filter` | `filter` |
| Get the first item                    | `array[0]`               | `List.head`   | `head`   |
| Get the first element that matches    | `Array.prototype.find`   | N/A           | `find`   |

## Other Common Data Structures

| Purpose         | JavaScript      | Elm            | Haskell  |
|-----------------|-----------------|----------------|----------|
| Optional values | `null`          | `Maybe`        | `Maybe`  |
| Error handling  | `try` / `catch` | `Result`       | `Either` |
| Async work      | `Promise`       | `Task`         | `IO`     |
| Side effects    | N/A             | `Task` / `Cmd` | `IO`     |

## Operators

Haskell is notorious for its use of operators. Here's how Elm concepts line up
with some of the most common Haskell operators. Most of these FP operations
don't exist in JavaScript (yet).

For more details on the Haskell operators, check out this [guide].

| Description           | JavaScript         | Elm                                         | Haskell |
|-----------------------|--------------------|---------------------------------------------|---------|
| Forwards pipe         | \|> (experimental) | \|>                                         | `&`     |
| Backwards pipe        |                    | <\|                                         | `$`     |
| Mapping               |                    | various `map` functions                     | `<$>`   |
| Applying              |                    | various (third party) `andMap` functions    | `<*>`   |
| Chaining              |                    | various `andThen` and `concatMap` functions | `>>=`   |
| Appending             | `+`                | `++`                                        | `<>`    |
| Backwards composition |                    | `<<`                                        | `.`     |
| Forwards composition  |                    | `>>`                                        |         |
| Alternative           |                    | various (third party) `or` functions        | <\|>    |

[guide]: https://haskell-lang.org/tutorial/operators

## Convenience functions

| Purpose                          | JavaScript | Elm        | Haskell |
|----------------------------------|------------|------------|---------|
| return the argument              | N/A        | `identity` | `id`    |
| ignore the second argument       | N/A        | `always`   | `const` |
| flip the arguments of a function | N/A        | `flip`     | `flip`  |
| treat two-tuple as two args      | N/A        | `curry`    | `curry` |
