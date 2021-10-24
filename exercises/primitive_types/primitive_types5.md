>! Compiling of exercises/primitive_types/primitive_types5.rs failed! Please try again. Here's the output:
>error: expected pattern, found `=`
> --> exercises/primitive_types/primitive_types5.rs:9:33
>  |
>9 |     let /* your pattern here */ = cat;
>  |                                 ^ expected pattern
>
>error: aborting due to previous error

```rust
// Origin
fn main() {
    let cat = ("Furry McFurson", 3.5);
    let /* your pattern here */ = cat;

    println!("{} is {} years old.", name, age);
}
```

```rust
// Solution
fn main() {
    let cat = ("Furry McFurson", 3.5);
    let (name,age) = cat;

    println!("{} is {} years old.", name, age);
}
```