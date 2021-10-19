>! Compiling of exercises/variables/variables6.rs failed! Please try again. Here's the output:
>error: missing type for `const` item
> --> exercises/variables/variables6.rs:6:7
>  |
>6 | const NUMBER = 3;
>  |       ^^^^^^ help: provide a type for the item: `NUMBER: i32`
>
>error: aborting due to previous error

```rust
//Origin
const NUMBER = 3;
fn main() {
    println!("Number {}", NUMBER);
}
```

```rust
//Solutions
const NUMBER :i32  = 3;
fn main() {
    println!("Number {}", NUMBER);
}
```

For this, adding the data types to `NUMBER` by following rust syntax will compile `variables6.rs`.