#### General Notes
>  * a `crate` is a package of reusable code
>  * bring input/output library into scope (from standard library)
>  * bring libraries into scope explicity with `use` keyword
>  * binary crates are executables, library crates have code meant for other programs
>  * `main` function is entry point into program
>  * `Crates.io` is the main repository for open source rust libraries
>  * `Cargo.lock` locks all your dependencies with semantic versioning unless you explicitly change the version
>  * the `let` keyword is used to create variables
>  * run `cargo doc --open` to see all documentation for your dependencies in your browser
>  * once a pattern is matched in a `match` statement, the program exits out of that block

#### [Simple Guessing Game](http://rust-lang.github.io/book/second-edition/ch02-00-guessing-game-tutorial.html)
```rust
extern crate rand;

use std::io;
use std::cmp::Ordering;
use rand::Rng;

fn main() {
    // println! is a macro
    println!("Guess the number I am thinking of");
    let lower_range = 1;
    let upper_range = 100;
    let secret_number = rand::thread_rng().gen_range(lower_range, upper_range + 1);
    // let secret_number = secret_number.to_string();
    loop {
        println!("Please guess a number between {} and {}: ", lower_range, upper_range);
        // in rust, variables are immutable by default, but the `mut` keyword allows mutability
        // :: -> association, `new` is associated function of `String` type (static method)
        let mut guess = String::new();
        // call the `stdin` method from the `io` library on first line of program
        // io::stdin() returns handle to standard input for terminal
        // .readline(str x) gets input from user and returns io::Result
        // string target of .readline(str x) must be mutable to accept value
        // & -> reference, and references are immutable by default, therefore need &mut
        io::stdin().read_line(&mut guess)
                   .expect("Failed to read in line");
        // shadow previous string value of `guess` with an immutable int32 version of `guess`
        let guess: u32 = match guess.trim().parse() {
            Ok(num)    => num,
            Err(_) => {
                println!("I'm sorry, your input ({}) is invalid, please try again...", guess);
                continue;
            }
        };
        println!("You guessed {}", guess);

        if guess > upper_range || guess < lower_range {
            println!("Your guess was outside the guess limits, please try again...");
            continue;
        }

        match guess.cmp(&secret_number) {
            Ordering::Less    => println!("Your guess was too small..."),
            Ordering::Greater => println!("Your guess was too large..."),
            Ordering::Equal   => {
                println!("Your guess was correct, you win!");
                break;
            }
        }
    }


    println!("The secret number was {}", secret_number);
    string_interpolation();
}

fn string_interpolation() {
    let x = "Joseph";
    let y = "Choi";
    // {} is a placeholder that holds a value in place (string interpolation)
    // multiple string interpolation values can be used so long as they are in order
    println!("My full name is {} {}", x, y);
}
```
