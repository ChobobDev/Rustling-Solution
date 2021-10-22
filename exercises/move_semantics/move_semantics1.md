>! Compiling of exercises/move_semantics/move_semantics1.rs failed! Please try again. Here's the output:
>error[E0596]: cannot borrow `vec1` as mutable, as it is not declared as mutable
>  --> exercises/move_semantics/move_semantics1.rs:13:5
>   |
>9  |     let vec1 = fill_vec(vec0);
>   |         ---- help: consider changing this to be mutable: `mut vec1`
>...
>13 |     vec1.push(88);
>   |     ^^^^ cannot borrow as mutable
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0596`.

```rust
// Origin
fn main() {
    let vec0 = Vec::new();

    let vec1 = fill_vec(vec0);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}
```

```rust
// Solution
fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}
```

We just need to make `vec1` mutable.