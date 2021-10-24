>! Compiling of exercises/primitive_types/primitive_types1.rs failed! Please try again. Here's the output:
>error: expected identifier, found keyword `if`
>  --> exercises/primitive_types/primitive_types1.rs:16:5
>   |
>16 |     if is_evening {
>   |     ^^ expected identifier, found keyword
>
>error: expected one of `:`, `;`, `=`, `@`, or `|`, found `is_evening`
>  --> exercises/primitive_types/primitive_types1.rs:16:8
>   |
>16 |     if is_evening {
>   |        ^^^^^^^^^^ expected one of `:`, `;`, `=`, `@`, or `|`
>
>error: aborting due to 2 previous errors

```rust
// Origin
fn main() {
    // Booleans (`bool`)

    let is_morning = true;
    if is_morning {
        println!("Good morning!");
    }

    let // Finish the rest of this line like the example! Or make it be false!
    if is_evening {
        println!("Good evening!");
    }
}
```

```rust
// Solution
fn main() {
    // Booleans (`bool`)

    let is_morning = true;
    if is_morning {
        println!("Good morning!");
    }

    let is_evening = false;// Finish the rest of this line like the example! Or make it be false!
    if is_evening {
        println!("Good evening!");
    }
}
```