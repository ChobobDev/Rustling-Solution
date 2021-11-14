>! Compiling of exercises/collections/vec1.rs failed! Please try again. Here's the output:
>error: expected `;`, found `}`
>  --> exercises/collections/vec1.rs:13:11
>   |
>13 |     (a, v)
>   |           ^ help: add `;` here
>14 | }
>   | - unexpected token
>
>error[E0425]: cannot find value `v` in this scope
>  --> exercises/collections/vec1.rs:13:9
>   |
>13 |     (a, v)
>   |         ^ help: a local variable with a similar name exists: `a`
>
>error[E0308]: mismatched types
> --> exercises/collections/vec1.rs:9:23
>  |
>9 | fn array_and_vec() -> ([i32; 4], Vec<i32>) {
>  |    -------------      ^^^^^^^^^^^^^^^^^^^^ expected tuple, found `()`
>  |    |
>  |    implicitly returns `()` as its body has no tail or `return` expression
>  |
>  = note:  expected tuple `([i32; 4], Vec<i32>)`
>          found unit type `()`
>
>error: aborting due to 3 previous errors
>
>Some errors have detailed explanations: E0308, E0425.
>For more information about an error, try `rustc --explain E0308`.

```rust
// Origin
fn array_and_vec() -> ([i32; 4], Vec<i32>) {
    let a = [10, 20, 30, 40]; // a plain array
    let v = // TODO: declare your vector here with the macro for vectors

    (a, v)
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_array_and_vec_similarity() {
        let (a, v) = array_and_vec();
        assert_eq!(a, v[..]);
    }
}

```

```rust
// Solution
fn array_and_vec() -> ([i32; 4], Vec<i32>) {
    let a = [10, 20, 30, 40]; // a plain array
    let v = vec![10,20,30,40];// TODO: declare your vector here with the macro for vectors

    (a, v)
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_array_and_vec_similarity() {
        let (a, v) = array_and_vec();
        assert_eq!(a, v[..]);
    }
}

```

