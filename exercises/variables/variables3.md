>! Compiling of exercises/variables/variables3.rs failed! Please try again. Here's the output:
>error[E0384]: cannot assign twice to immutable variable `x`
> --> exercises/variables/variables3.rs:9:5
>  |
>7 |     let x = 3;
>  |         -
>  |         |
>  |         first assignment to `x`
>  |         help: consider making this binding mutable: `mut x`
>8 |     println!("Number {}", x);
>9 |     x = 5; // don't change this line
>  |     ^^^^^ cannot assign twice to immutable variable
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0384`.
>
>Welcome to watch mode! You can type 'help' to get an overview of the commands you can use here.

```rust
//origin
fn main() {
    let x = 3;
    println!("Number {}", x);
    x = 5; // don't change this line
    println!("Number {}", x);
}
```

```rust
//solution
fn main() {
    let mut x = 3;
    println!("Number {}", x);
    x = 5; // don't change this line
    println!("Number {}", x);
}
```
by making variable x mutable by adding `mut` will let `variable3.rs` be compiled.