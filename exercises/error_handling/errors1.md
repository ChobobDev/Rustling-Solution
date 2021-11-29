>! Compiling of exercises/error_handling/errors1.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
>  --> exercises/error_handling/errors1.rs:37:9
>   |
>37 | /         assert_eq!(
>38 | |             generate_nametag_text("".into()),
>39 | |             Err("`name` was empty; it must be nonempty.".into())
>40 | |         );
>   | |__________^ expected enum `Option`, found enum `Result`
>   |
>   = note: expected enum `Option<String>`
>              found enum `Result<_, _>`
>   = note: this error originates in the macro `assert_eq` (in Nightly builds, run with -Z macro-backtrace for more info)
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0308`.

```rust
// Origin
pub fn generate_nametag_text(name: String) -> Option<String> {
    if name.len() > 0 {
        Some(format!("Hi! My name is {}", name))
    } else {
        // Empty names aren't allowed.
        None
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    // This test passes initially if you comment out the 2nd test.
    // You'll need to update what this test expects when you change
    // the function under test!
    #[test]
    fn generates_nametag_text_for_a_nonempty_name() {
        assert_eq!(
            generate_nametag_text("Beyoncé".into()),
            Some("Hi! My name is Beyoncé".into())
        );
    }

    #[test]
    fn explains_why_generating_nametag_text_fails() {
        assert_eq!(
            generate_nametag_text("".into()),
            Err("`name` was empty; it must be nonempty.".into())
        );
    }
}
```

```rust
// Solution
pub fn generate_nametag_text(name: String) -> Result<String, String> {
    if name.len() > 0 {
        Ok(format!("Hi! My name is {}", name))
    } else {
        // Empty names aren't allowed.
        Err(String::from("`name` was empty; it must be nonempty."))
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    // This test passes initially if you comment out the 2nd test.
    // You'll need to update what this test expects when you change
    // the function under test!
    #[test]
    fn generates_nametag_text_for_a_nonempty_name() {
        assert_eq!(
            generate_nametag_text("Beyoncé".into()),
            Ok("Hi! My name is Beyoncé".into())
        );
    }

    #[test]
    fn explains_why_generating_nametag_text_fails() {
        assert_eq!(
            generate_nametag_text("".into()),
            Err("`name` was empty; it must be nonempty.".into())
        );
    }
}

```