>! Compiling of exercises/if/if1.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
> --> exercises/if/if1.rs:5:34
>  |
>5 | pub fn bigger(a: i32, b: i32) -> i32 {
>  |        ------                    ^^^ expected `i32`, found `()`
>  |        |
>  |        implicitly returns `()` as its body has no tail or `return` expression
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0308`.

```rust
// Origin
pub fn bigger(a: i32, b: i32) -> i32 {
    // Complete this function to return the bigger number!
    // Do not use:
    // - another function call
    // - additional variables
    // Execute `rustlings hint if1` for hints
}
```

```rust
// Solution
pub fn bigger(a: i32, b: i32) -> i32 {
    // Complete this function to return the bigger number!
    // Do not use:
    // - another function call
    // - additional variables
    // Execute `rustlings hint if1` for hints
    if a>b {a} else {b}
}
```

