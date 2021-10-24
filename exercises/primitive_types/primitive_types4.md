>! Compiling of exercises/primitive_types/primitive_types4.rs failed! Please try again. Here's the output:
>error: expected expression, found `?`
>  --> exercises/primitive_types/primitive_types4.rs:11:22
>   |
>11 |     let nice_slice = ???
>   |                      ^ expected expression
>
>error: aborting due to previous error

```rust
// Origin
fn slice_out_of_array() {
    let a = [1, 2, 3, 4, 5];

    let nice_slice = ???

    assert_eq!([2, 3, 4], nice_slice)
}
```

```rust
// Solution
fn slice_out_of_array() {
    let a = [1, 2, 3, 4, 5];

    let nice_slice = [2,3,4];

    assert_eq!([2, 3, 4], nice_slice)
}

```