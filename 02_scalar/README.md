# 02_scalar.rs

1. 타입
    1. integers (signed, unsigned)
        - i8, i16, i32, i64, i128, and isize (plus + minus sign)
        - u8, u16,, u32, u64, u128, and usize(plus sign)
        - isize , usize: compter architecture에 따른 것
            - isize -> 32비트 -> i32
            - isize -> 64비트 -> i64
        - ex. let my_number = 100; // i32
        - type inference
            ```rust
            let my_number : u8 = 100 ;  //255
            let my_other_number = 50 ;  //i32
            let third_number = my_number + my_other_number ;
            ```
            -> 컴파일 오류 : my_number는 u8, my_other_number는 명시되지 않아 i32 타입 달라 X


    2. char (4bytes)
        - ex.
            ```rust
            let first_letter = 'A';
            let space = ' '; 
            let other_language_char = 'Ꮔ'; 
            let cat_face = '😺'; // 이모지
            ```


    3. casting = simple type change using 'as'
        ```rust
        let my_number : u16 = 8 ;
        let second_number : u8 = 10 ;
        let third_number = my_number + second_number as u16 ;
        ```
        +error X
        +let my_number = 9_u8;
        +let other_number=1_000_000_000u64;

        ```rust
        let my_number = 'a' as u8 ;
        println!("My number is {}", my_number) ;
        ```
        -> My number is 97

    // use std::mem::sizeof
    // println!("Sizeof a char: {}", size_of::<char>()) ;


    4. char 2
        ```rust
        fn main() {
        println!("Size of a char: {}", std::mem::size_of::<char>()); // 4 bytes
        println!("Size of string containing 'a': {}", "a".len()); // .len() gives the size of the string in bytes
        println!("Size of string containing 'ß': {}", "ß".len());
        println!("Size of string containing '国': {}", "国".len());
        println!("Size of string containing '𓅱': {}", "𓅱".len());
        }
        ```

        ```rust
        fn main() {
        let slice = "Hello!";
        println!("Slice is {} bytes and also {} characters.", slice.len(), slice.chars().count()); //chars.count 글자수 세기
        let slice2 = "안녕!";
        println!("Slice2 is {} bytes but only {} characters.", slice2.len(), slice2.chars().count());
        } //7,3
        ```
        "Hello there" -> ('H', 'e', 'l').count()


    5. float
        ```rust
        fn main(){
            let my_number = 9. ; // float f64
            let other_number = 9 ; //i32
        }
        ```
    
    6. print
        ```rust

        fn give() ->i32 {
            //->는 함수의 반환 타입 지정
            27 //return 27
        }
        fn main(){
            let my_name ="yerim" ;
            //let my_age = "27" ;
            println!("My name is {} and my age is {}", my_name, give()) ;

        }
        ```

        ```rust
        //string interpolation
        //2. 이름 지정자 사용
        fn main(){
            let my_city = "Seoul" ;
            let year = 2025 ;
            let population = 96585633;
            println!(
                "The city of {city} in {year} had a population of {population}",
                city = my_city,
                year = year,
                population = population
            );
        }
        ```

        ```rust
        //3. 위치 지정자 사용

        fn main(){
            let my_city = "Seoul" ;
            let year = 2025 ;
            let population = 96585633;
            println!(
                "The city of {0} in {1} had a population of {2}. I love {0}",
                my_city,
                year,
                population
            );
        }
        ```
        
        ```rust
        //현재 가능

         fn main(){
            let city = "Seoul" ;
            let year = 2025 ;
            let population = 96585633;
            println!(
                "The city of {city} in {year} had a population of {population}. I love {city}",
            );
        }
        ```

        ```rust
        fn main(){
            print!("This\nis\wendy\n") ;
            print(r#"c:\thisdrive\new_drive"#);  //raw text
            print!(
            "SUNKISS
            웬디솔로3집
            9월10일") ;
            
            let my_variable= 9000 ;
            println!("{:X}", my_variable) ;
            //{:X} = 정수를 16진수로 출력하라 (대문자로, {:x}는 소문자로)

            let my_variable= 14 ;
            println!("{:b}", my_variable) ;
            //{:b}= 2진수로 출력
            //u8 = 부호가 없는 8비트 정수 타입

        }

    7. empty tuple
        ```rust
        // () - empty tuple,unit type(void)
        fn empty_tuple(){
            
        }
        fn main() {
            let tuple = empty_tuple();
            tuple;
            6
        }
        ```

        ```rust
        //Dispaly {}
        //Debug print
        fn empty_tuple(){
            
        }
        fn main() {
            let tuple = empty_tuple();
            println!("{:?}", tuple);
        }
        ```

