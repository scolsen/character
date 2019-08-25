# Character 

Character is a small utility library for working with (for the moment, only
roman alpha) characters in Carp. It introduces the `Character` data type which
abstracts over the base implementation of characters, enabling you to work with
characters more flexibly. Character supports the following features:

- Compatibility with the `(match)` macro.
- Type-based restriction to a fixed character set.

Additionally, this library provides a number of convenient functions for working
with characters, such as `lower` and `upper`. 

## Examples

- Convert the first letter of a string from uppercase to lowercase:

```clojure
(defn convert [string] 
  (Character.lower (Character.from-char (head string))))

;; (convert "Alpha") => "a"
```

- Check whether a given character is roman and non-numeric:

```clojure 
(defn check-roman [char]
  (match (Character.from-char char)
    (Invalid) flase
    _ true))
```

## Alternatives 

This library is predominantly one of style and convenience. The vast majority of
its functionality can be implemented using Carp's base `Char` type, and Carp
also provides several comparable utility functions. The major benefit of this
library is stylistic: if you prefer structuring programs using pattern matching
over types, this library facilitates doing so with characters.

## Future Plans

Eventually, I'd like to support general interfaces for defining restrictive
sumtype character classes similar to the one first elaborated here.
