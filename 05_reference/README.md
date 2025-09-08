# 05_reference.rs

1. reference : word가 변수 지칭하는 관계
    ```rust
    fn main() {
        let my_number = 15; // This is an i32
        let single_reference = &my_number; //  This is a &i32
        let double_reference = &single_reference; // This is a &&i32
        let five_references = &&&&&my_number; // This is a &&&&&i32
    }
    ```

2. pointer : 특정 메모리의 위치를 나타내는 양의 정수(값을 나타내는 id)
- pointer vaiable : 포인터 값 가지는 변수
- ex. r : 0xfsddfe  -> r = pointer variable, 0xfsddfe = pointer
     ```rust
     fn main () {
        let v : i32 = 2025 ;
        let r = &v ; //r이 가리키는 값이 v가 가리키는 값과 같게, &v는 값이 출력됨
        // let r : &i32 = &v ;
        //r의 변수 타입이 &i32(i32 값에 대한 참조 타입)

        println!("v:{}, r:{:p}", v, r) ;
        //v:2025, r:0x8bf50ffaac
        //{ :p} -> 포인터 값으로 표현할 수 있으면 표현해라
        
        let mut v : i32 = 2026 ;  //섀도잉,위에 v
        let p = &mut v ;
        // p 통해 v값 바꿀 수 있음
        //&mut : 가능하면 mut 쓰지 마라 ~ 헷갈리니까

        *p = 2024 ;
        //* = reference가 가리키는 대상이 바뀐다 (reference 자체를 바꾸는 경우가 있기 때문에 * 사용)
        //reference가 가리키는 대상 = v
        println!("{}",  p); //2024

        let mut p = &mut v ; //mut p = p라는 변수 자체에 다른 값을 할당할 수 있다
        //p는 이제 v를 가리키며 v를 변경할 수 있음
        //새로운 p 변수 선언(shadowing) -> 근데 여전히 얘도 v를 가리키고 있으므로, v의 값 2024를 출력
        let mut w = 9999 ;
        println!("{}",  p); //2024

        p =  &mut w ;
        *p = 10000 ;
        println!("{}",  p); //10000
    }

        