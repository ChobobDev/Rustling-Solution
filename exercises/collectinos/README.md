# Collections

Rust’s standard library includes a number of very useful data
structures called collections. Most other data types represent one
specific value, but collections can contain multiple values. Unlike
the built-in array and tuple types, the data these collections point
to is stored on the heap, which means the amount of data does not need
to be known at compile time and can grow or shrink as the program
runs.

This exercise will get you familiar with two fundamental data
structures that are used very often in Rust programs:

* A *vector* allows you to store a variable number of values next to
  each other.
* A *hash map* allows you to associate a value with a particular key.
  You may also know this by the names [*unordered map* in C++](https://en.cppreference.com/w/cpp/container/unordered_map), 
  [*dictionary* in Python](https://docs.python.org/3/tutorial/datastructures.html#dictionaries) or an *associative array* in other languages.

## Further information

- [Storing Lists of Values with Vectors](https://doc.rust-lang.org/stable/book/ch08-01-vectors.html)
- [Storing Keys with Associated Values in Hash Maps](https://doc.rust-lang.org/book/ch08-03-hash-maps.html)

## Progress
| Exercies          | date  | Code |
| :---------------: | :-------: | :---------: |
| vec1.rs | 14/11/2021    | [:link:](./vec1.md) |
| vec2.rs | 15/11/2021    | [:link:](./vec2.md) |
| hashmap1.rs | 16/11/2021    | [:link:](./hashmap1.md) |
| hashmap2.rs | 17/11/2021    | [:link:](./hashmap2.md) |