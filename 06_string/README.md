# 06_string.rs

1. &str, string
    ```rust
    fn main(){
        let name : &str = "김예림" ;
        //name = 지칭하는 레퍼런스 (가볍게)
        let other_name : String = String :: from("I love my yerim") ;
        //<-  String이라는 객체 (무겁게)
        println!("{:?} {:?}", name, other_name) ;
        // { :?} = 디버깅 정보 출력
        let together = format!("1: {}, 2:{}", name, other_name) ;
        // format! = string 합쳐서 넣어주는거, String 타입의 새로운 문자열을 생성하여 반환하는 역할
        // 함수가 아니라 매크로임을 명시적으로 나타내기 위해 !를 붙임
        dbg!(name, other_name) ;
        // dbg! = 디버깅 정보 출력

        //println!({:?}): 내가 원하는 형식으로 변수 값을 출력하고 싶을 때 사용
        //dbg!: 변수 이름, 위치 등 자세한 디버깅 정보를 함께 보면서 값을 확인하고 싶을 때 사용, 특히 함수의 반환 값이나 복잡한 표현식의 중간 값을 확인하는 데 탁월
    }