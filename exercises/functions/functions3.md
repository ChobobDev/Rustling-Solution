>! Compiling of exercises/functions/functions3.rs failed! Please try again. Here's the output:
>error[E0061]: this function takes 1 argument but 0 arguments were supplied
>  --> exercises/functions/functions3.rs:7:5
>   |
>7  |     call_me();
>   |     ^^^^^^^-- supplied 0 arguments
>   |     |
>   |     expected 1 argument
>   |
>note: function defined here
>  --> exercises/functions/functions3.rs:10:4
>   |
>10 | fn call_me(num: u32) {
>   |    ^^^^^^^ --------
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0061`.

```rust
// Origin
fn main() {
    call_me();
}

fn call_me(num: u32) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

```rust
// Solution
fn main() {
    call_me(5);
}

fn call_me(num: u32) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

In this case by passing a value to `fn call_me()` will let `functions3.rs` be compiled.

