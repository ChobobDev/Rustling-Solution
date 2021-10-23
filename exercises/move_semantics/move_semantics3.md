>! Compiling of exercises/move_semantics/move_semantics3.rs failed! Please try again. Here's the output:
>error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
>  --> exercises/move_semantics/move_semantics3.rs:21:5
>   |
>20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
>   |             --- help: consider changing this to be mutable: `mut vec`
>21 |     vec.push(22);
>   |     ^^^ cannot borrow as mutable
>
>error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
>  --> exercises/move_semantics/move_semantics3.rs:22:5
>   |
>20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
>   |             --- help: consider changing this to be mutable: `mut vec`
>21 |     vec.push(22);
>22 |     vec.push(44);
>   |     ^^^ cannot borrow as mutable
>
>error[E0596]: cannot borrow `vec` as mutable, as it is not declared as mutable
>  --> exercises/move_semantics/move_semantics3.rs:23:5
>   |
>20 | fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
>   |             --- help: consider changing this to be mutable: `mut vec`
>...
>23 |     vec.push(66);
>   |     ^^^ cannot borrow as mutable
>
>error: aborting due to 3 previous errors
>
>For more information about this error, try `rustc --explain E0596`.

```rust
// Origin
fn fill_vec(vec: Vec<i32>) -> Vec<i32> {
    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```

```rust
// Solution
fn fill_vec(mut vec: Vec<i32>) -> Vec<i32> {
    vec.push(22);
    vec.push(44);
    vec.push(66);

    vec
}
```
