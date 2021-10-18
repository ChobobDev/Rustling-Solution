>! Compiling of exercises/variables/variables1.rs failed! Please try again. Here's the output:
>error[E0425]: cannot find value `x` in this scope
>  --> exercises/variables/variables1.rs:12:5
>   |
>12 |     x = 5;
>   |     ^ not found in this scope
>
>error[E0425]: cannot find value `x` in this scope
>  --> exercises/variables/variables1.rs:13:36
>   |
>13 |     println!("x has the value {}", x);
>   |                                    ^ not found in this scope
>
>error: aborting due to 2 previous errors
>
>For more information about this error, try `rustc --explain E0425`.
>
>Welcome to watch mode! You can type 'help' to get an overview of the commands you can use here.

```rust
//Origin
fn main() {
    x = 5;
    println!("x has the value {}", x);
}
```

```rust
//Solution
fn main() {
    let x = 5;
    println!("x has the value {}", x);
}
```

By adding let will compile `variables1.rs`