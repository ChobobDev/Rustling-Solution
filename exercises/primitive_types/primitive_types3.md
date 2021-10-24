>! Compiling of exercises/primitive_types/primitive_types3.rs failed! Please try again. Here's the output:
>error: expected expression, found `?`
> --> exercises/primitive_types/primitive_types3.rs:8:13
>  |
>8 |     let a = ???
>  |             ^ expected expression
>
>error: aborting due to previous error

```rust
// Origin
fn main() {
    let a = ???

    if a.len() >= 100 {
        println!("Wow, that's a big array!");
    } else {
        println!("Meh, I eat arrays like that for breakfast.");
    }
}
```

```rust
// Solution
fn main() {
    let a = ["B","e","r","n","i","e","i","s","a","w","e","s","o","m","e"];

    if a.len() >= 100 {
        println!("Wow, that's a big array!");
    } else {
        println!("Meh, I eat arrays like that for breakfast.");
    }
}
```