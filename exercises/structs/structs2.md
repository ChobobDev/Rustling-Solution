>! Compiling of exercises/structs/structs2.rs failed! Please try again. Here's the output:
>error[E0609]: no field `name` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:38:31
>   |
>38 |         assert_eq!(your_order.name, "Hacker in Rust");
>   |                               ^^^^
>
>error[E0609]: no field `year` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:39:31
>   |
>39 |         assert_eq!(your_order.year, order_template.year);
>   |                               ^^^^
>
>error[E0609]: no field `made_by_phone` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:40:31
>   |
>40 |         assert_eq!(your_order.made_by_phone, order_template.made_by_phone);
>   |                               ^^^^^^^^^^^^^
>
>error[E0609]: no field `made_by_mobile` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:41:31
>   |
>41 |         assert_eq!(your_order.made_by_mobile, order_template.made_by_mobile);
>   |                               ^^^^^^^^^^^^^^
>
>error[E0609]: no field `made_by_email` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:42:31
>   |
>42 |         assert_eq!(your_order.made_by_email, order_template.made_by_email);
>   |                               ^^^^^^^^^^^^^
>
>error[E0609]: no field `item_number` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:43:31
>   |
>43 |         assert_eq!(your_order.item_number, order_template.item_number);
>   |                               ^^^^^^^^^^^
>
>error[E0609]: no field `count` on type `fn() {tests::your_order}`
>  --> exercises/structs/structs2.rs:44:31
>   |
>44 |         assert_eq!(your_order.count, 1);
>   |                               ^^^^^
>
>error: aborting due to 7 previous errors
>
>For more information about this error, try `rustc --explain E0609`.

```rust
// Origin
#[derive(Debug)]
struct Order {
    name: String,
    year: u32,
    made_by_phone: bool,
    made_by_mobile: bool,
    made_by_email: bool,
    item_number: u32,
    count: u32,
}

fn create_order_template() -> Order {
    Order {
        name: String::from("Bob"),
        year: 2019,
        made_by_phone: false,
        made_by_mobile: false,
        made_by_email: true,
        item_number: 123,
        count: 0,
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn your_order() {
        let order_template = create_order_template();
        // TODO: Create your own order using the update syntax and template above!
        // let your_order =
        assert_eq!(your_order.name, "Hacker in Rust");
        assert_eq!(your_order.year, order_template.year);
        assert_eq!(your_order.made_by_phone, order_template.made_by_phone);
        assert_eq!(your_order.made_by_mobile, order_template.made_by_mobile);
        assert_eq!(your_order.made_by_email, order_template.made_by_email);
        assert_eq!(your_order.item_number, order_template.item_number);
        assert_eq!(your_order.count, 1);
    }
}

```

```rust
// Solution
#[derive(Debug)]
struct Order {
    name: String,
    year: u32,
    made_by_phone: bool,
    made_by_mobile: bool,
    made_by_email: bool,
    item_number: u32,
    count: u32,
}

fn create_order_template() -> Order {
    Order {
        name: String::from("Bob"),
        year: 2019,
        made_by_phone: false,
        made_by_mobile: false,
        made_by_email: true,
        item_number: 123,
        count: 0,
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn your_order() {
        let order_template = create_order_template();
        // TODO: Create your own order using the update syntax and template above!
        let your_order = Order{
            name: String::from("Hacker in Rust"),
            count: 1,
            ..order_template
        };
        assert_eq!(your_order.name, "Hacker in Rust");
        assert_eq!(your_order.year, order_template.year);
        assert_eq!(your_order.made_by_phone, order_template.made_by_phone);
        assert_eq!(your_order.made_by_mobile, order_template.made_by_mobile);
        assert_eq!(your_order.made_by_email, order_template.made_by_email);
        assert_eq!(your_order.item_number, order_template.item_number);
        assert_eq!(your_order.count, 1);
    }
}

```