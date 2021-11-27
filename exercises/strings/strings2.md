>! Compiling of exercises/strings/strings2.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
> --> exercises/strings/strings2.rs:9:24
>  |
>9 |     if is_a_color_word(word) {
>  |                        ^^^^
>  |                        |
>  |                        expected `&str`, found struct `String`
>  |                        help: consider borrowing here: `&word`
>
>error: aborting due to previous error

```rust
// Origin
fn main() {
    let word = String::from("green"); // Try not changing this line :)
    if is_a_color_word(word) {
        println!("That is a color word I know!");
    } else {
        println!("That is not a color word I know.");
    }
}

fn is_a_color_word(attempt: &str) -> bool {
    attempt == "green" || attempt == "blue" || attempt == "red"
}
```

```rust
// Solution
fn main() {
    let word = String::from("green"); // Try not changing this line :)
    if is_a_color_word(&word) {
        println!("That is a color word I know!");
    } else {
        println!("That is not a color word I know.");
    }
}

fn is_a_color_word(attempt: &str) -> bool {
    attempt == "green" || attempt == "blue" || attempt == "red"
}
```