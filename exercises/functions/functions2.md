>! Compiling of exercises/functions/functions2.rs failed! Please try again. Here's the output:
>error: expected type, found `)`
>  --> exercises/functions/functions2.rs:10:16
>   |
>10 | fn call_me(num:) {
>   |                ^ expected type
>
>error[E0425]: cannot find value `num` in this scope
>  --> exercises/functions/functions2.rs:11:17
>   |
>11 |     for i in 0..num {
>   |                 ^^^ not found in this scope
>
>error: aborting due to 2 previous errors
>
>For more information about this error, try `rustc --explain E0425`.

```rust
// Origin
fn main() {
    call_me(3);
}

fn call_me(num:) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

```rust
// Solution
fn main() {
    call_me(3);
}

fn call_me(num:i32) {
    for i in 0..num {
        println!("Ring! Call number {}", i + 1);
    }
}
```

By defining the types of parameter `num` in `fn call_me()` will help `functions2.rs` be compiled.