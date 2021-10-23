>! Compiling of exercises/move_semantics/move_semantics4.rs failed! Please try again. Here's the output:
>error[E0423]: expected value, found macro `vec`
>  --> exercises/move_semantics/move_semantics4.rs:23:19
>   |
>23 |     let mut vec = vec;
>   |                   ^^^ not a value
>   |
>help: use `!` to invoke the macro
>   |
>23 |     let mut vec = vec!;
>   |                      ^
>
>error[E0061]: this function takes 0 arguments but 1 argument was supplied
>  --> exercises/move_semantics/move_semantics4.rs:12:20
>   |
>12 |     let mut vec1 = fill_vec(vec0);
>   |                    ^^^^^^^^ ---- supplied 1 argument
>   |                    |
>   |                    expected 0 arguments
>   |
>note: function defined here
>  --> exercises/move_semantics/move_semantics4.rs:22:4
>   |
>22 | fn fill_vec() -> Vec<i32> {
>   |    ^^^^^^^^
>
>error: aborting due to 2 previous errors
>
>Some errors have detailed explanations: E0061, E0423.
>For more information about an error, try `rustc --explain E0061`.

```rust
// Origin
fn main() {
    let vec0 = Vec::new();

    let mut vec1 = fill_vec(vec0);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

// `fill_vec()` no longer takes `vec: Vec<i32>` as argument
fn fill_vec() -> Vec<i32> {
    let mut vec = vec;

    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

```rust
// Solution
fn main() {

    let mut vec1 = fill_vec();

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);

    vec1.push(88);

    println!("{} has length {} content `{:?}`", "vec1", vec1.len(), vec1);
}

// `fill_vec()` no longer takes `vec: Vec<i32>` as argument
fn fill_vec() -> Vec<i32> {
    let mut vec = Vec::new();

    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```