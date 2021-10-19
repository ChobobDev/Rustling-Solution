>! Compiling of exercises/variables/variables4.rs failed! Please try again. Here's the output:
>error[E0381]: borrow of possibly-uninitialized variable: `x`
> --> exercises/variables/variables4.rs:8:27
>  |
>8 |     println!("Number {}", x);
>  |                           ^ use of possibly-uninitialized `x`
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0381`.

```rust
//origin
fn main() {
    let x: i32;
    println!("Number {}", x);
}
```

```rust
//resolution
fn main() {
    let x: i32 = 414;
    println!("Number {}", x);
}
```

For this, we just need to initialize the variable `x` following rust syntax.