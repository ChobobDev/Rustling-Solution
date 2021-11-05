>! Compiling of exercises/enums/enums1.rs failed! Please try again. Here's the output:
>error[E0599]: no variant or associated item named `Quit` found for enum `Message` in the current scope
>  --> exercises/enums/enums1.rs:12:31
>   |
>7  | enum Message {
>   | ------------ variant or associated item `Quit` not found here
>...
>12 |     println!("{:?}", Message::Quit);
>   |                               ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Echo` found for enum `Message` in the current scope
>  --> exercises/enums/enums1.rs:13:31
>   |
>7  | enum Message {
>   | ------------ variant or associated item `Echo` not found here
>...
>13 |     println!("{:?}", Message::Echo);
>   |                               ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Move` found for enum `Message` in the current scope
>  --> exercises/enums/enums1.rs:14:31
>   |
>7  | enum Message {
>   | ------------ variant or associated item `Move` not found here
>...
>14 |     println!("{:?}", Message::Move);
>   |                               ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `ChangeColor` found for enum `Message` in the current scope
>  --> exercises/enums/enums1.rs:15:31
>   |
>7  | enum Message {
>   | ------------ variant or associated item `ChangeColor` not found here
>...
>15 |     println!("{:?}", Message::ChangeColor);
>   |                               ^^^^^^^^^^^ variant or associated item not found in `Message`
>
>error: aborting due to 4 previous errors
>
>For more information about this error, try `rustc --explain E0599`.

```rust

// Origin
enum Message {
    // TODO: define a few types of messages as used below
}

fn main() {
    println!("{:?}", Message::Quit);
    println!("{:?}", Message::Echo);
    println!("{:?}", Message::Move);
    println!("{:?}", Message::ChangeColor);
}
```

```rust
// Solution
enum Message {
    // TODO: define a few types of messages as used below
    Quit,
    Echo,
    Move,
    ChangeColor,
}

fn main() {
    println!("{:?}", Message::Quit);
    println!("{:?}", Message::Echo);
    println!("{:?}", Message::Move);
    println!("{:?}", Message::ChangeColor);
}

```