>! Compiling of exercises/variables/variables2.rs failed! Please try again. Here's the output:
>error[E0282]: type annotations needed
> --> exercises/variables/variables2.rs:7:9
>  |
>7 |     let x;
>  |         ^ consider giving `x` a type
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0282`.

```rust
//Origin
fn main() {
    let x;
    if x == 10 {
        println!("Ten!");
    } else {
        println!("Not ten!");
    }
}
```

```rust
//Solution
fn main() {
    let x= 5;
    if x == 10 {
        println!("Ten!");
    } else {
        println!("Not ten!");
    }
}
```
initializing x could help `variables2.rs` to be compiled.
