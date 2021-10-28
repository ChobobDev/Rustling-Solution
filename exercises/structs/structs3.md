>! Compiling of exercises/structs/structs3.rs failed! Please try again. Here's the output:
>error: expected identifier, found `?`
>  --> exercises/structs/structs3.rs:29:36
>   |
>16 | impl Package {
>   |              - while parsing this item list starting here
>...
>29 |     fn is_international(&self) -> ??? {
>   |                                    ^ expected identifier
>...
>36 | }
>   | - the item list ends here
>
>error: expected expression, found `?`
>  --> exercises/structs/structs3.rs:76:30
>   |
>76 |         let cents_per_gram = ???;
>   |                              ^ expected expression
>
>error[E0308]: mismatched types
>  --> exercises/structs/structs3.rs:18:33
>   |
>18 |           if weight_in_grams <= 0 {
>   |  _________________________________^
>19 | |             // Something goes here...
>20 | |         } else {
>   | |_________^ expected struct `Package`, found `()`
>
>error[E0599]: no method named `is_international` found for struct `Package` in the current scope
>  --> exercises/structs/structs3.rs:58:25
>   |
>10 | struct Package {
>   | -------------- method `is_international` not found for this
>...
>58 |         assert!(package.is_international());
>   |                         ^^^^^^^^^^^^^^^^ method not found in `Package`
>
>error[E0599]: no method named `is_international` found for struct `Package` in the current scope
>  --> exercises/structs/structs3.rs:68:26
>   |
>10 | struct Package {
>   | -------------- method `is_international` not found for this
>...
>68 |         assert!(!package.is_international());
>   |                          ^^^^^^^^^^^^^^^^ method not found in `Package`
>
>error: aborting due to 5 previous errors
>
>Some errors have detailed explanations: E0308, E0599.
>For more information about an error, try `rustc --explain E0308`.

```rust
// Origin
#[derive(Debug)]
struct Package {
    sender_country: String,
    recipient_country: String,
    weight_in_grams: i32,
}

impl Package {
    fn new(sender_country: String, recipient_country: String, weight_in_grams: i32) -> Package {
        if weight_in_grams <= 0 {
            // Something goes here...
        } else {
            return Package {
                sender_country,
                recipient_country,
                weight_in_grams,
            };
        }
    }

    fn is_international(&self) -> ??? {
        // Something goes here...
    }

    fn get_fees(&self, cents_per_gram: i32) -> ??? {
        // Something goes here...
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    #[should_panic]
    fn fail_creating_weightless_package() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Austria");

        Package::new(sender_country, recipient_country, -2210);
    }

    #[test]
    fn create_international_package() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Russia");

        let package = Package::new(sender_country, recipient_country, 1200);

        assert!(package.is_international());
    }

    #[test]
    fn create_local_package() {
        let sender_country = String::from("Canada");
        let recipient_country = sender_country.clone();

        let package = Package::new(sender_country, recipient_country, 1200);

        assert!(!package.is_international());
    }

    #[test]
    fn calculate_transport_fees() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Spain");

        let cents_per_gram = ???;

        let package = Package::new(sender_country, recipient_country, 1500);

        assert_eq!(package.get_fees(cents_per_gram), 4500);
    }
}

```

```rust
// Solution
#[derive(Debug)]
struct Package {
    sender_country: String,
    recipient_country: String,
    weight_in_grams: i32,
}

impl Package {
    fn new(sender_country: String, recipient_country: String, weight_in_grams: i32) -> Package {
        if weight_in_grams <= 0 {
            // Something goes here...
            panic!()
        } else {
            return Package {
                sender_country,
                recipient_country,
                weight_in_grams,
            };
        }
    }

    fn is_international(&self) -> bool {
        // Something goes here...
        self.sender_country != self.recipient_country
    }

    fn get_fees(&self, cents_per_gram: i32) -> i32 {
        // Something goes here...
        (self.weight_in_grams * cents_per_gram + (1000 / 2)) / 1000
    }
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    #[should_panic]
    fn fail_creating_weightless_package() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Austria");

        Package::new(sender_country, recipient_country, -2210);
    }

    #[test]
    fn create_international_package() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Russia");

        let package = Package::new(sender_country, recipient_country, 1200);

        assert!(package.is_international());
    }

    #[test]
    fn create_local_package() {
        let sender_country = String::from("Canada");
        let recipient_country = sender_country.clone();

        let package = Package::new(sender_country, recipient_country, 1200);

        assert!(!package.is_international());
    }

    #[test]
    fn calculate_transport_fees() {
        let sender_country = String::from("Spain");
        let recipient_country = String::from("Spain");

        let cents_per_gram = 3000;

        let package = Package::new(sender_country, recipient_country, 1500);

        assert_eq!(package.get_fees(cents_per_gram), 4500);
    }
}
```