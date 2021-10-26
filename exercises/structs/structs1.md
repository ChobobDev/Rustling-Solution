>! Compiling of exercises/structs/structs1.rs failed! Please try again. Here's the output:
>error[E0425]: cannot find value `green` in this scope
>  --> exercises/structs/structs1.rs:24:20
>   |
>24 |         assert_eq!(green.name, "green");
>   |                    ^^^^^ not found in this scope
>
>error[E0425]: cannot find value `green` in this scope
>  --> exercises/structs/structs1.rs:25:20
>   |
>25 |         assert_eq!(green.hex, "#00FF00");
>   |                    ^^^^^ not found in this scope
>
>error[E0425]: cannot find value `green` in this scope
>  --> exercises/structs/structs1.rs:33:20
>   |
>33 |         assert_eq!(green.0, "green");
>   |                    ^^^^^ not found in this scope
>
>error[E0425]: cannot find value `green` in this scope
>  --> exercises/structs/structs1.rs:34:20
>   |
>34 |         assert_eq!(green.1, "#00FF00");
>   |                    ^^^^^ not found in this scope
>
>error[E0425]: cannot find value `unit_struct` in this scope
>  --> exercises/structs/structs1.rs:41:49
>   |
>41 |         let message = format!("{:?}s are fun!", unit_struct);
>   |                                                 ^^^^^^^^^^^ not found in this scope
>
>warning: unused import: `super::*`
>  --> exercises/structs/structs1.rs:17:9
>   |
>17 |     use super::*;
>   |         ^^^^^^^^
>   |
>   = note: `#[warn(unused_imports)]` on by default
>
>error: aborting due to 5 previous errors; 1 warning emitted
>
>For more information about this error, try `rustc --explain E0425`.
>
>Welcome to watch mode! You can type 'help' to get an overview of the commands you can use here.

```rust
// Origin
struct ColorClassicStruct {
    // TODO: Something goes here
}

struct ColorTupleStruct(/* TODO: Something goes here */);

#[derive(Debug)]
struct UnitStruct;

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn classic_c_structs() {
        // TODO: Instantiate a classic c struct!
        // let green =

        assert_eq!(green.name, "green");
        assert_eq!(green.hex, "#00FF00");
    }

    #[test]
    fn tuple_structs() {
        // TODO: Instantiate a tuple struct!
        // let green =

        assert_eq!(green.0, "green");
        assert_eq!(green.1, "#00FF00");
    }

    #[test]
    fn unit_structs() {
        // TODO: Instantiate a unit struct!
        // let unit_struct =
        let message = format!("{:?}s are fun!", unit_struct);

        assert_eq!(message, "UnitStructs are fun!");
    }
}
```

```rust
// Solution
struct ColorClassicStruct {
    // TODO: Something goes here
    name: String,
    hex: String,
}

struct ColorTupleStruct(String, String);

#[derive(Debug)]
struct UnitStruct;

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn classic_c_structs() {
        // TODO: Instantiate a classic c struct!
        let green = ColorClassicStruct{
            name: String::from("green"),
            hex: String::from("#00FF00"),

        };

        assert_eq!(green.name, "green");
        assert_eq!(green.hex, "#00FF00");
    }

    #[test]
    fn tuple_structs() {
        // TODO: Instantiate a tuple struct!
        let green = ColorTupleStruct(
            String::from("green"),
            String::from("#00FF00"),
        );

        assert_eq!(green.0, "green");
        assert_eq!(green.1, "#00FF00");
    }

    #[test]
    fn unit_structs() {
        // TODO: Instantiate a unit struct!
        let unit_struct = UnitStruct;
        let message = format!("{:?}s are fun!", unit_struct);

        assert_eq!(message, "UnitStructs are fun!");
    }
}


```