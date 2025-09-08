# 03_variable.rs

1. mutability
- immutability : 값을 바꿀 수 X, 변수는 어떤값 지정 심볼
- immutable by default, mut
```rust
fn main(){
    let my_number = 10;
    my_number = 9;
    //error

    let mut my_number = 10;
    my_number = 9;

}
```

2. shadowing
- 같은 이름을 다시 쓰는 것
```rust
fn main() {
    let my_variable = 10;
    let my_variable = "My variable";
    println!("{}", my_variable);
}
```
-> My variable
- 가장 가까이 있는 정의를 사용

```rust
fn main() {
    let my_variable = 10;
    println!("{}", my_variable);  //10
    {
        let my_variable = "My variable";
        println!("{}", my_variable);  //Myvarialbe
    }
    
    println!("{}", my_variable);  //10
}
```