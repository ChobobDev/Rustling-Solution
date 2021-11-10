>! Compiling of exercises/modules/modules1.rs failed! Please try again. Here's the output:
>error[E0603]: function `make_sausage` is private
>  --> exercises/modules/modules1.rs:19:22
>   |
>19 |     sausage_factory::make_sausage();
>   |                      ^^^^^^^^^^^^ private function
>   |
>note: the function `make_sausage` is defined here
>  --> exercises/modules/modules1.rs:12:5
>   |
>12 |     fn make_sausage() {
>   |     ^^^^^^^^^^^^^^^^^
>
>error: aborting due to previous error
>
>For more information about this error, try `rustc --explain E0603`.

```rust
// Origin
mod sausage_factory {
    // Don't let anybody outside of this module see this!
    fn get_secret_recipe() -> String {
        String::from("Ginger")
    }

    fn make_sausage() {
        get_secret_recipe();
        println!("sausage!");
    }
}

fn main() {
    sausage_factory::make_sausage();
}

```

```rust
// Solution
mod sausage_factory {
    // Don't let anybody outside of this module see this!
    fn get_secret_recipe() -> String {
        String::from("Ginger")
    }

    pub fn make_sausage() {
        get_secret_recipe();
        println!("sausage!");
    }
}

fn main() {
    sausage_factory::make_sausage();
}

```