>! Testing of exercises/collections/vec2.rs failed! Please try again. Here's the output:
>
>running 1 test
>test tests::test_vec_loop ... FAILED
>
>successes:
>
>successes:
>
>failures:
>
>---- tests::test_vec_loop stdout ----
>thread 'tests::test_vec_loop' panicked at 'assertion failed: `(left == right)`
>  left: `[2, 4, 6, 8, 10]`,
> right: `[4, 8, 12, 16, 20]`', exercises/collections/vec2.rs:31:9
>note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
>
>
>failures:
>    tests::test_vec_loop
>
>test result: FAILED. 0 passed; 1 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s

```rust
// Origin
fn vec_loop(mut v: Vec<i32>) -> Vec<i32> {
    for i in v.iter_mut() {
        // TODO: Fill this up so that each element in the Vec `v` is
        // multiplied by 2.
    }

    // At this point, `v` should be equal to [4, 8, 12, 16, 20].
    v
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_vec_loop() {
        let v: Vec<i32> = (1..).filter(|x| x % 2 == 0).take(5).collect();
        let ans = vec_loop(v.clone());

        assert_eq!(ans, v.iter().map(|x| x * 2).collect::<Vec<i32>>());
    }
}

```

```rust
// Solution
fn vec_loop(mut v: Vec<i32>) -> Vec<i32> {
    for i in v.iter_mut() {
        // TODO: Fill this up so that each element in the Vec `v` is
        // multiplied by 2.
        *i *=2;
    }

    // At this point, `v` should be equal to [4, 8, 12, 16, 20].
    v
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_vec_loop() {
        let v: Vec<i32> = (1..).filter(|x| x % 2 == 0).take(5).collect();
        let ans = vec_loop(v.clone());

        assert_eq!(ans, v.iter().map(|x| x * 2).collect::<Vec<i32>>());
    }
}

```