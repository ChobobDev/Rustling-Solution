>! Compiling of exercises/functions/functions4.rs failed! Please try again. Here's the output:
>error: expected type, found `{`
>  --> exercises/functions/functions4.rs:14:30
>   |
>14 | fn sale_price(price: i32) -> {
>   |                              ^ expected type
>
>error: aborting due to previous error

```rust
// Origin
fn main() {
    let original_price = 51;
    println!("Your sale price is {}", sale_price(original_price));
}

fn sale_price(price: i32) -> {
    if is_even(price) {
        price - 10
    } else {
        price - 3
    }
}

fn is_even(num: i32) -> bool {
    num % 2 == 0
}
```

```rust
// Solution
fn main() {
    let original_price = 51;
    println!("Your sale price is {}", sale_price(original_price));
}

fn sale_price(price: i32) -> i32 {
    if is_even(price) {
        price - 10
    } else {
        price - 3
    }
}

fn is_even(num: i32) -> bool {
    num % 2 == 0
}

```

By defining the return data type of `fn sale_price()` will help `functions4.rs` be compiled.