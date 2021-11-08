>! Compiling of exercises/enums/enums2.rs failed! Please try again. Here's the output:
>error[E0599]: no variant named `Move` found for enum `Message`
>  --> exercises/enums/enums2.rs:19:18
>   |
>7  | enum Message {
>   | ------------ variant `Move` not found here
>...
>19 |         Message::Move { x: 10, y: 30 },
>   |                  ^^^^ variant not found in `Message`
>
>error[E0599]: no variant or associated item named `Echo` found for enum `Message` in the current scope
>  --> exercises/enums/enums2.rs:20:18
>   |
>7  | enum Message {
>   | ------------ variant or associated item `Echo` not found here
>...
>20 |         Message::Echo(String::from("hello world")),
>   |                  ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `ChangeColor` found for enum `Message` in the current scope
>  --> exercises/enums/enums2.rs:21:18
>   |
>7  | enum Message {
>   | ------------ variant or associated item `ChangeColor` not found here
>...
>21 |         Message::ChangeColor(200, 255, 255),
>   |                  ^^^^^^^^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Quit` found for enum `Message` in the current scope
>  --> exercises/enums/enums2.rs:22:18
>   |
>7  | enum Message {
>   | ------------ variant or associated item `Quit` not found here
>...
>22 |         Message::Quit,
>   |                  ^^^^ variant or associated item not found in `Message`
>
>error: aborting due to 4 previous errors
>
>For more information about this error, try `rustc --explain E0599`.

```rust
// Origin
enum Message {
    // TODO: define the different variants used below
    
}

impl Message {
    fn call(&self) {
        println!("{:?}", &self);
    }
}

fn main() {
    let messages = [
        Message::Move { x: 10, y: 30 },
        Message::Echo(String::from("hello world")),
        Message::ChangeColor(200, 255, 255),
        Message::Quit,
    ];

    for message in &messages {
        message.call();
    }
}

```

```rust
// Solution
enum Message {
    // TODO: define the different variants used below
    Move { x: i32, y: i32 },
    Echo(String),
    ChangeColor(i32, i32, i32),
    Quit,

}

impl Message {
    fn call(&self) {
        println!("{:?}", &self);
    }
}

fn main() {
    let messages = [
        Message::Move { x: 10, y: 30 },
        Message::Echo(String::from("hello world")),
        Message::ChangeColor(200, 255, 255),
        Message::Quit,
    ];

    for message in &messages {
        message.call();
    }
}

```