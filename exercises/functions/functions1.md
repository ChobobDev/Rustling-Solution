>! Compiling of exercises/functions/functions1.rs failed! Please try again. Here's the output:
>error[E0425]: cannot find function `call_me` in this scope
> --> exercises/functions/functions1.rs:7:5
>  |
>7 |     call_me();
>  |     ^^^^^^^ not found in this scope
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0425`.

```rust
//Origin
fn main() {
    call_me();
}
```

```rust
//Solutions
fn main() {
    call_me();
}

fn call_me(){
    println!("Seongbin Bernie Cho")
}
```

For this by defining a function `call_me()` will make `functions1.rs` be compiled.