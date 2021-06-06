#                            Rust Learning

##### Setup on mac or linux

```$ curl https://sh.rustup.rs -sSf | sh```

##### update

```$ rustup update```

##### version

``` $ rustup —version```

```$ rustc —version```

##### uninstall

``` $ rustup self uninstall```

##### offline Book

``` $ rustup docs --book```

##### Project Dev

* useful command

  **Cargo**  build management

  >``` $ cargo new bolts-with-rust``` // new project, - -help command has more options
  >
  >```$ cargo build``` // compiles & generates executable 
  >
  >``` $ cargo run``` // build and run in one step 
  >
  >``` $ cargo check``` //compiles but dont create executable
  >
  >``` $ cargo build —release``` // for release build which is much fast creating target/release instead of target/debug
  >
  >```$ cargo doc —open ``` //which will build documentation provided by all of your dependencies locally and open it in your browser
  >
  >```$ cargo test```  // for running test in parallel
  >
  >```$ cargo test — —test-threads=1``` //run tests one after other
  >
  >```$ cargo test -- —nocapture```  // to see println statement when test cases passed, by default if failed  output statements are see on command line.
  >
  >```$ cargo test <testname>``` // to run only one test
  >
  >```$ cargo test <any part ofthe name> // to run all tests that contain the part of  name```
  >
  >```$ cargo test -- —ignored``` // to run ignored tests
  >
  >```$ cargo test --test integration_test``` //run only an integration_test.rs file in tests folder.

##### Data Types

1. Scalar (single value)

   * Integer :

     | Length  | Signed  | Unsigned |
     | ------- | ------- | -------- |
     | 8-bit   | `i8`    | `u8`     |
     | 16-bit  | `i16`   | `u16`    |
     | 32-bit  | `i32`   | `u32`    |
     | 64-bit  | `i64`   | `u64`    |
     | 128-bit | `i128`  | `u128`   |
     | arch    | `isize` | `usize`  |

   * float : f32 & f64(default)

   * character : char  four bytes in size and represents a Unicode Scalar Value

   * Boolean : bool true or false ( 1 byte)

2. Compound

   * Tuple : General way of grouping together a number of values with a **variety** of types into one compound type. Tuples have a fixed length: once declared, they cannot grow or shrink in size.

     ```rust
     let x: (i32, f64, u8) = (500, 6.4, 1);
     let five_hundred = x.0;
     ```

   * Array : Unlike a tuple, every element of an array must have the same type. Arrays in Rust are different from arrays in some other languages because arrays in Rust have a fixed length, like tuples.

     ```rust
     let months = ["January", "February", "March", "April", "May", "June", "July",
                   "August", "September", "October", "November", "December"];
     let first = month[0];
     ```

     > Arrays are useful when you want your data allocated on the stack rather than the heap  or when you want to ensure you always have a fixed number of elements. An array isn’t as flexible as the vector type, though. **A vector is a similar collection type provided by the standard library that *is* allowed to grow or shrink in size**. If you’re unsure whether to use an array or a vector, you should probably use a vector.

##### Functions

Rust code uses *snake case* as the conventional style for function and variable names. In snake case, all letters are lowercase and underscores separate words

```rust
fn another_function(x: i32) {
    println!("Another function.");
}
```

##### Ownership

**Rules:**

- Each value in Rust has a variable that’s called its *owner*.
- There can only be one owner at a time.
- When the owner goes out of scope, the value will be dropped.

Stack  - last in first out, fast 

Heap - Finds the space to store the data and that pointer of that space is stored in stach for reference

> **All data stored on the stack must have a known, fixed size**. Data with an unknown size at compile time or a size that might change must be stored on the heap instead. The heap is less organized: when you put data on the heap, you request a certain amount of space. The memory allocator finds an empty spot in the heap that is big enough, marks it as being in use, and returns a *pointer*, which is the address of that location. **This process is called *allocating on the heap* and is sometimes abbreviated as just *allocating*.** Pushing values onto the stack is not considered allocating. Because the pointer is a known, fixed size, you can store the pointer on the stack, but when you want the actual data, you must follow the pointer.

Above data types covered are stored on stack.

###### The String type vs string literals

​	string literals, where a string value is hardcoded into our program. String literals are convenient, but they aren’t suitable for every situation in which we may want to use text. One reason is that they’re immutable. Another is that not every string value can be known when we write our code: for example, what if we want to take user input and store it? For these situations, Rust has a second string type, `String`. This type is allocated on the heap and as such is able to store an amount of text that is unknown to us at compile time.

```rust
let s = String::from("hello");
s.push_str(", world!"); // push_str() appends a literal to a String
println!("{}", s); // This will print `hello, world!`
```

#### Memory and Allocation

In the case of a string literal, we know the contents at compile time, so the text is hardcoded directly into the final executable. This is why string literals are fast and efficient. But these properties only come from the string literal’s immutability. Unfortunately, we can’t put a blob of memory into the binary for each piece of text whose size is unknown at compile time and whose size might change while running the program.

Rust will never automatically create “deep” copies of your data. Therefore, any *automatic* copying can be assumed to be inexpensive in terms of runtime performance.

> #### Clone: used for deep copy so that s1 is still valid
>
> ```rust
>  let s1 = String::from("hello");
>  let s2 = s1.clone();
>  println!("s1 = {}, s2 = {}", s1, s2);
> ```
>
> #### Stack-Only Data: Copy
>
> ```rust
> let x = 5;
> let y = x;
> println!("x = {}, y = {}", x, y);	
> ```
>
> The reason is that types such as integers that have a known size at compile time are stored entirely on the stack, so copies of the actual values are quick to make. That means there’s no reason we would want to prevent `x` from being valid after we create the variable `y`. In other words, there’s no difference between deep and shallow copying here, so calling `clone` wouldn’t do anything different from the usual shallow copying and we can leave it out.

#### The Rules of References

- At any given time, you can have *either* one mutable reference *or* any number of immutable references.
- References must always be valid.

### The Slice Type

Another data type that does not have ownership is the *slice*. Slices let you reference a contiguous sequence of elements in a collection rather than the whole collection.

### Structs

```rust
struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}
```

* truple structs : ex:- struct Color(i32, i32, i32);

* unit-like structs : structs that don’t have any fields! These are called *unit-like structs* because they behave similarly to `()`, the unit type

* Method's :   methods are different from functions in that they’re defined within the context of a struct (or an enum or a trait object, which we cover in Chapters 6 and 17, respectively), and their first parameter is always `self`, which represents the instance of the struct the method is being called on.

  ```rust
  #[derive(Debug)]
  struct Rectangle {
      width: u32,
      height: u32,
  }
  
  impl Rectangle {
      fn area(&self) -> u32 {
          self.width * self.height
      }
  }
  ```

* Associated functions :  Another useful feature of `impl` blocks is that we’re allowed to define functions within `impl` blocks that *don’t* take `self` as a parameter. These are called *associated functions* because they’re associated with the struct. They’re still functions, not methods, because they don’t have an instance of the struct to work with. You’ve already used the `String::from` associated function. Associated functions are often used for constructors that will return a new instance of the struct

