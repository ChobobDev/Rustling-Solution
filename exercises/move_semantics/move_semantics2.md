>! Compiling of exercises/move_semantics/move_semantics2.rs failed! Please try again. Here's the output:
>error[E0382]: borrow of moved value: `vec0`
>  --> exercises/move_semantics/move_semantics2.rs:13:57
>   |
>8  |     let vec0 = Vec::new();
>   |         ---- move occurs because `vec0` has type `Vec<i32>`, which does not implement the `Copy` trait
>9  |
>10 |     let mut vec1 = fill_vec(vec0);
>   |                             ---- value moved here
>...
>13 |     println!("{} has length {} content `{:?}`", "vec0", vec0.len(), vec0);
>   |                                                         ^^^^ value borrowed here after move
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0382`.
>
>Welcome to watch mode! You can type 'help' to get an overview of the commands you can use here.

```rust
// Origin
fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    // Do not change the following line!
    println!("{} has length {} content `{:?}`", "vec0", vec0.len(), vec0);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}
```

```rust
// Solution
fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    let vec0 = vec1.clone();

    // Do not change the following line!
    println!("{} has length {} content `{:?}`", "vec0", vec0.len(), vec0);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}
```