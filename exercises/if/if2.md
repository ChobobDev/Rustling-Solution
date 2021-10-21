>! Compiling of exercises/if/if2.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
>  --> exercises/if/if2.rs:13:9
>   |
>13 |         1
>   |         ^ expected `&str`, found integer
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0308`.
>
>Welcome to watch mode! You can type 'help' to get an overview of the commands you can use here.

```rust
// Origin
pub fn fizz_if_foo(fizzish: &str) -> &str {
    if fizzish == "fizz" {
        "foo"
    } else {
        1
    }
}
```

```rust
// Solution
pub fn fizz_if_foo(fizzish: &str) -> &str {
    if fizzish == "fizz" {
        "foo"
    } else if fizzish == "fuzz" {
        "bar"
    } else {
        "baz"
    }
}
```

We just need to finish `if` statement as the question guided. 