MiniLisp with string type
=========================

This is an extension of Rui Ueyama's MiniLisp to support strings.

All the docs in the original
[README](https://github.com/rui314/minilisp/blob/master/README.md)

apply, adding the following operators:

### Literals

Added string literal, like `"string"`

    (define a "this is a string") -> "this is a string"

### String operators

`string-append` takes a list of strings and concatenates it

    (string-append "string1" "string2" "string3") -> "string1string2string3"

`substring` returns a slice of the original string, accepting the starting
index and optionally the end index. If the end is not specified, go up the
end of the original string

    (substring "this is a string" 3 9) -> "s is a"
    (substring "this is a string" 3) -> "s is a string"

`number->string` converts a number to a string
    (number->string 123) -> "123"

`string->number` converts a string to a number
    (string->number "123") -> 123

`number->byte` converts a number to an unsinged byte, appendable to a string
    (string-append (number->byte 195) (number->byte 161)) -> "á"

`string-length` returns the length _in bytes_ of a string
    (string-length "this is a example string") -> 22
    (string-length "áéí") -> 6
