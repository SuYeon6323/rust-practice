# 04_function.rs

1. function

        ```rust
        fn give_number(one: i32, two: i32) -> i32 {
            one * two  //반환값 -> 세미콜론X
        }

        fn main() {
            let my_number = give number(9, 8);
            println!("{}", my_number);
        }
        ```

        ```rust
        fn print_number(one: i32, two: i32) -> () {
            let multiplied = one * two;
            println!("{}", multiplied);
        }

        fn main() {
            print_number(7,8);
        }
        ```

        ```rust
        fn give_number(one: i16, two: i16) -> i16{
            let multiplied_by_ten = {
                let first_number = 10;
                first_number * one * two
            };
            multiplied_by_ten
        }

        fn main() {
            let my_number = give_number(9, 1) ;
            println!("{}", my_number);
        }
        ```

+ default -> i32, f64
+ 함수가 실행하는 main 밑에 있어도 됨