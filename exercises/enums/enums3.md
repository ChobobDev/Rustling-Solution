>! Compiling of exercises/enums/enums3.rs failed! Please try again. Here's the output:
>error[E0599]: no variant or associated item named `ChangeColor` found for enum `Message` in the current scope
>  --> exercises/enums/enums3.rs:54:32
>   |
>6  | enum Message {
>   | ------------ variant or associated item `ChangeColor` not found here
>...
>54 |         state.process(Message::ChangeColor((255, 0, 255)));
>   |                                ^^^^^^^^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Echo` found for enum `Message` in the current scope
>  --> exercises/enums/enums3.rs:55:32
>   |
>6  | enum Message {
>   | ------------ variant or associated item `Echo` not found here
>...
>55 |         state.process(Message::Echo(String::from("hello world")));
>   |                                ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Move` found for enum `Message` in the current scope
>  --> exercises/enums/enums3.rs:56:32
>   |
>6  | enum Message {
>   | ------------ variant or associated item `Move` not found here
>...
>56 |         state.process(Message::Move(Point { x: 10, y: 15 }));
>   |                                ^^^^ variant or associated item not found in `Message`
>
>error[E0599]: no variant or associated item named `Quit` found for enum `Message` in the current scope
>  --> exercises/enums/enums3.rs:57:32
>   |
>6  | enum Message {
>   | ------------ variant or associated item `Quit` not found here
>...
>57 |         state.process(Message::Quit);
>   |                                ^^^^ variant or associated item not found in `Message`
>
>error: aborting due to 4 previous errors
>
>For more information about this error, try `rustc --explain E0599`.

```rust
// Origin
enum Message {
    // TODO: implement the message variant types based on their usage below
    
}

struct Point {
    x: u8,
    y: u8,
}

struct State {
    color: (u8, u8, u8),
    position: Point,
    quit: bool,
}

impl State {
    fn change_color(&mut self, color: (u8, u8, u8)) {
        self.color = color;
    }

    fn quit(&mut self) {
        self.quit = true;
    }

    fn echo(&self, s: String) {
        println!("{}", s);
    }

    fn move_position(&mut self, p: Point) {
        self.position = p;
    }

    fn process(&mut self, message: Message) {
        // TODO: create a match expression to process the different message variants
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_match_message_call() {
        let mut state = State {
            quit: false,
            position: Point { x: 0, y: 0 },
            color: (0, 0, 0),
        };
        state.process(Message::ChangeColor((255, 0, 255)));
        state.process(Message::Echo(String::from("hello world")));
        state.process(Message::Move(Point { x: 10, y: 15 }));
        state.process(Message::Quit);

        assert_eq!(state.color, (255, 0, 255));
        assert_eq!(state.position.x, 10);
        assert_eq!(state.position.y, 15);
        assert_eq!(state.quit, true);
    }
}

```

```rust
// Solution
enum Message {
    // TODO: implement the message variant types based on their usage below
    ChangeColor((u8, u8, u8)),
    Echo(String),
    Move(Point),
    Quit,
}

struct Point {
    x: u8,
    y: u8,
}

struct State {
    color: (u8, u8, u8),
    position: Point,
    quit: bool,
}

impl State {
    fn change_color(&mut self, color: (u8, u8, u8)) {
        self.color = color;
    }

    fn quit(&mut self) {
        self.quit = true;
    }

    fn echo(&self, s: String) {
        println!("{}", s);
    }

    fn move_position(&mut self, p: Point) {
        self.position = p;
    }

    fn process(&mut self, message: Message) {
        // TODO: create a match expression to process the different message variants
        match message {
            Message::ChangeColor(color) => {
                self.change_color(color);
            }
            Message::Echo(string) => {
                self.echo(string)
            }
            Message::Move(point) => {
                self.move_position(point);
            }
            Message::Quit => {
                self.quit();
            }
        }
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn test_match_message_call() {
        let mut state = State {
            quit: false,
            position: Point { x: 0, y: 0 },
            color: (0, 0, 0),
        };
        state.process(Message::ChangeColor((255, 0, 255)));
        state.process(Message::Echo(String::from("hello world")));
        state.process(Message::Move(Point { x: 10, y: 15 }));
        state.process(Message::Quit);

        assert_eq!(state.color, (255, 0, 255));
        assert_eq!(state.position.x, 10);
        assert_eq!(state.position.y, 15);
        assert_eq!(state.quit, true);
    }
}

```