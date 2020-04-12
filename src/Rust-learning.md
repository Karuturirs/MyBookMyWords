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
