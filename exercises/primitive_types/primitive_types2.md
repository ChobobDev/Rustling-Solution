>! Compiling of exercises/primitive_types/primitive_types2.rs failed! Please try again. Here's the output:
>error: expected identifier, found keyword `if`
>  --> exercises/primitive_types/primitive_types2.rs:22:5
>   |
>22 |     if your_character.is_alphabetic() {
>   |     ^^ expected identifier, found keyword
>
>error: expected one of `:`, `;`, `=`, `@`, or `|`, found `your_character`
>  --> exercises/primitive_types/primitive_types2.rs:22:8
>   |
>22 |     if your_character.is_alphabetic() {
>   |        ^^^^^^^^^^^^^^ expected one of `:`, `;`, `=`, `@`, or `|`
>
>error: aborting due to 2 previous errors

```rust
// Origin
fn main() {
    // Characters (`char`)

    let my_first_initial = 'C';
    if my_first_initial.is_alphabetic() {
        println!("Alphabetical!");
    } else if my_first_initial.is_numeric() {
        println!("Numerical!");
    } else {
        println!("Neither alphabetic nor numeric!");
    }

    let // Finish this line like the example! What's your favorite character?
    // Try a letter, try a number, try a special character, try a character
    // from a different language than your own, try an emoji!
    if your_character.is_alphabetic() {
        println!("Alphabetical!");
    } else if your_character.is_numeric() {
        println!("Numerical!");
    } else {
        println!("Neither alphabetic nor numeric!");
    }
}

```

```rust
// Solution
fn main() {
    // Characters (`char`)

    let my_first_initial = 'C';
    if my_first_initial.is_alphabetic() {
        println!("Alphabetical!");
    } else if my_first_initial.is_numeric() {
        println!("Numerical!");
    } else {
        println!("Neither alphabetic nor numeric!");
    }

    let your_character = 'B';// Finish this line like the example! What's your favorite character?
    // Try a letter, try a number, try a special character, try a character
    // from a different language than your own, try an emoji!
    if your_character.is_alphabetic() {
        println!("Alphabetical!");
    } else if your_character.is_numeric() {
        println!("Numerical!");
    } else {
        println!("Neither alphabetic nor numeric!");
    }
}

```