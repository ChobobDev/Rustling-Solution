>! Compiling of exercises/strings/strings1.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
>--> exercises/strings/strings1.rs:13:5
>   |
>12 | fn current_favorite_color() -> String {
>   |                                ------ expected `String` because of return type
>13 |     "blue"
>   |     ^^^^^^- help: try using a conversion method: `.to_string()`
>   |     |
>   |     expected struct `String`, found `&str`
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0308`.

```rust
// Origin
fn main() {
    let answer = current_favorite_color();
    println!("My current favorite color is {}", answer);
}

fn current_favorite_color() -> String {
    "blue"
}

```

```rust
// Solution
fn main() {
    let answer = current_favorite_color();
    println!("My current favorite color is {}", answer);
}

fn current_favorite_color() -> String {
    "blue".to_string()
}

```
