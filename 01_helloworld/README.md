# 01_helloworld.rs

1.  fn : function


2.  println!
- print: print
- ln: 줄바꿈, 유라인
- ! : 뱅, 매크로


3. let rust : &str = "Rust" ;
- : 타입
- &str : 스트링 포인터
- rust라는 걸 쓸건데 타입이 &str


4. let rust = "Rust" ;
- 타입 인프런스: 타입 없어도 알아서 유추

5. 사용되지 않는 변수 경고 피하기
- 변수 이름 앞에 (_) 밑줄을 붙여 컴파일러에게 이 변수는 사용되지 않아도 괜찮음을 알려줌
- ex. let _x = 5 ;