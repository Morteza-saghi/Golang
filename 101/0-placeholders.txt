| Placeholder | Usage                                  | Output Example                  |
|-------------|----------------------------------------|----------------------------------|
| **%v**      | Default format for the value           | `fmt.Printf("%v", 42)` → `42`   |
| **%#v**     | Go-syntax representation of the value  | `fmt.Printf("%#v", []int{1,2})` → `[]int{1, 2}` |
| **%T**      | Type of the value                      | `fmt.Printf("%T", 42)` → `int`  |
| **%%**      | Literal percent sign                   | `fmt.Printf("%%")` → `%`        |
| **%d**      | Decimal integer (base 10)              | `fmt.Printf("%d", 42)` → `42`   |
| **%b**      | Binary representation                  | `fmt.Printf("%b", 42)` → `101010`|
| **%c**      | Character corresponding to the Unicode code point | `fmt.Printf("%c", 65)` → `A` |
| **%x**      | Hexadecimal (lowercase)                | `fmt.Printf("%x", 255)` → `ff`  |
| **%X**      | Hexadecimal (uppercase)                | `fmt.Printf("%X", 255)` → `FF`  |
| **%o**      | Octal representation                   | `fmt.Printf("%o", 42)` → `52`   |
| **%q**      | Quoted string or character             | `fmt.Printf("%q", 'A')` → `'A'` |
| **%s**      | String (plain text)                    | `fmt.Printf("%s", "Hello")` → `Hello` |
| **%p**      | Pointer address                        | `fmt.Printf("%p", &x)` → `0xc000018098` |
| **%f**      | Floating-point number (default precision) | `fmt.Printf("%f", 3.14)` → `3.140000` |
| **%.nf**    | Floating-point with `n` decimal places | `fmt.Printf("%.2f", 3.14159)` → `3.14` |
| **%e**      | Scientific notation (lowercase)        | `fmt.Printf("%e", 1234.567)` → `1.234567e+03` |
| **%E**      | Scientific notation (uppercase)        | `fmt.Printf("%E", 1234.567)` → `1.234567E+03` |
| **%t**      | Boolean value                          | `fmt.Printf("%t", true)` → `true` |
| **%U**      | Unicode format (U+ followed by hex)    | `fmt.Printf("%U", 'A')` → `U+0041` |
| **%g**      | Compact floating-point or scientific   | `fmt.Printf("%g", 1234.567)` → `1234.567` |
| **%G**      | Same as %g but using uppercase for scientific notation | `fmt.Printf("%G", 1234.567)` → `1234.567` |
