>! Compiling of exercises/primitive_types/primitive_types6.rs failed! Please try again. Here's the output:
>error: expected expression, found `?`
>  --> exercises/primitive_types/primitive_types6.rs:12:18
>   |
>12 |     let second = ???;
>   |                  ^ expected expression
>
>error: aborting due to previous error

```rust
// Origin
fn indexing_tuple() {
    let numbers = (1, 2, 3);
    // Replace below ??? with the tuple indexing syntax.
    let second = ???;

    assert_eq!(2, second,
        "This is not the 2nd number in the tuple!")
}
```

```rust
// Solution
fn indexing_tuple() {
    let numbers = (1, 2, 3);
    // Replace below ??? with the tuple indexing syntax.
    let second = numbers.1;

    assert_eq!(2, second,
        "This is not the 2nd number in the tuple!")
}
```