>! Compiling of exercises/quiz1.rs failed! Please try again. Here's the output:
>error[E0425]: cannot find function `calculate_apple_price` in this scope
>  --> exercises/quiz1.rs:18:18
>   |
>18 |     let price1 = calculate_apple_price(35);
>   |                  ^^^^^^^^^^^^^^^^^^^^^ not found in this scope
>
>error[E0425]: cannot find function `calculate_apple_price` in this scope
>  --> exercises/quiz1.rs:19:18
>   |
>19 |     let price2 = calculate_apple_price(40);
>   |                  ^^^^^^^^^^^^^^^^^^^^^ not found in this scope
>
>error[E0425]: cannot find function `calculate_apple_price` in this scope
>  --> exercises/quiz1.rs:20:18
>   |
>20 |     let price3 = calculate_apple_price(65);
>   |                  ^^^^^^^^^^^^^^^^^^^^^ not found in this scope
>
>error: aborting due to 3 previous errors
>
>For more information about this error, try `rustc --explain E0425`.

```rust
// Origin
// fn calculate_apple_price {

```

```rust
// Solution
fn calculate_apple_price(piece: i32) -> i32{
    if piece <= 40 {piece*2}else{piece}
}
```