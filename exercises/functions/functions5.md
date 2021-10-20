>! Compiling of exercises/functions/functions5.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
>  --> exercises/functions/functions5.rs:11:24
>   |
>11 | fn square(num: i32) -> i32 {
>   |    ------              ^^^ expected `i32`, found `()`
>   |    |
>   |    implicitly returns `()` as its body has no tail or `return` expression
>12 |     num * num;
>   |              - help: consider removing this semicolon
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0308`.

```rust
/// Origin
fn main() {
    let answer = square(3);
    println!("The answer is {}", answer);
}

fn square(num: i32) -> i32 {
    num * num;
}
```

```rust
/// Solution
fn main() {
    let answer = square(3);
    println!("The answer is {}", answer);
}

fn square(num: i32) -> i32 {
    num * num
}

```

As the error message guided, by removing `;` will resolve the issue.