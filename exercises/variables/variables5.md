>! Compiling of exercises/variables/variables5.rs failed! Please try again. Here's the output:
>error[E0308]: mismatched types
> --> exercises/variables/variables5.rs:9:14
>  |
>9 |     number = 3;
>  |              ^ expected `&str`, found integer
>
>error[E0369]: cannot add `{integer}` to `&str`
>  --> exercises/variables/variables5.rs:10:48
>   |
>10 |     println!("Number plus two is : {}", number + 2);
>   |                                         ------ ^ - {integer}
>   |                                         |
>   |                                         &str
>
>error: aborting due to 2 previous errors

```rust
///Origin
fn main() {
    let number = "T-H-R-E-E"; // don't change this line
    println!("Spell a Number : {}", number);
    number = 3;
    println!("Number plus two is : {}", number + 2);
}
```

```rust
///Solution
fn main() {
    let number = "T-H-R-E-E"; // don't change this line
    println!("Spell a Number : {}", number);
    let number = 3;
    println!("Number plus two is : {}", number + 2);
}
```

To make `variables5.rs` compiled , we need to re-initialize the variable `x`.
