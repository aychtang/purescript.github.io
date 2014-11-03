---
title: Home
---

## PureScript is a small strongly typed programming language that compiles to JavaScript.

### Features

- Algebraic data types
- Pattern matching
- Type inference
- Type classes
- Higher kinded types
- Rank-N types
- Extensible records
- Extensible effects
- Modules
- Simple FFI
- No runtime system
- Human-readable output

### Example

```haskell
module Main where

import Prelude ((++))

class Show a where
  show :: a -> String

instance showString :: Show String where
  show s = s

instance showBoolean :: Show Boolean where
  show true = "true"
  show false = "false"

instance showArray :: (Show a) => Show [a] where
  show arr = "[" ++ go arr ++ "]"
    where
    go :: forall a. (Show a) => [a] -> String
    go [] = ""
    go [x] = show x
    go (x:xs) = show x ++ ", " ++ go xs

test = show [true, false]
```
