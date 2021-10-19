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

```

```rust
///Solution
```
