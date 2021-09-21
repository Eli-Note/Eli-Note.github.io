---
layout: single
title: "코틀린 공부중"
---

# 📢 기본 문법 - 작성중
___

## 📚함수
<br>

> 구문식 
``` kotlin
fun sum(a: Int, b: Int): Int {

    return a + b

}
```
>표현식
``` kotlin
fun sum(a: Int, b: Int) = a + b

fun max(a: Int, b: Int) = if (a>b) a else b
```

📌자바와의 차이점

- 메소드 표시로 메소드명 앞에 ' fun '을 붙여줌.

- 자료형 int를 Int로 표기

- 파라메터작성을 ' 인자값: 자료형 ' 으로 작성한다.

- 리턴형을 메소드명 앞이 아닌 파라메터 가로()의 우측에 ' : ' 를 열고서 우측에 써준다.

- void의 경우 void생략 가능.
___


## 📚 Value, Variable(변수)와 데이터 형식
<br>

### 📙Value, Variable(변수)
``` kotlin 
var d: String = "처음이자 마지막 초기화"

val b = 2L //  L -> short타입과 구분 짓기
val c = 3.14f //  f -> Double과 구분 짓기

val d: String // 선언
d = "null값이 안되도록 초기화 진행"
val a: Int = 1 // 생성

val e: String? // ? -> null값 존재 가능

var ary = ArrayList<Int>(1)
ary!!.add(99)

val boolNull: boolean? = null
```

📌자바와의 차이점
- final(고정값)을 val로 표시하고 final이 아닌경우 var로 표시
<bar>

- 타입추론이 가능하므로 자료형 생략가능
<bar>

- 기본적으로 null값이 들어가는 것이 불가능
<bar>

- null값을 넣고싶을 경우 자료형 우측에 '?'를 붙이기
<bar>

- ' ? '이 널값 존재표기라면 반대로 널값 불가능표기는 변수명우측에' !! '로 표기
<bar>

- ' ? '이 붙으면 null값이 들어왔을때 skip가능
<br>
<br>

### 📙데이터 형식 (기본형 변수)

|분류|키워드|크기|최소 ~ 최대|
|:--:|:--:|:--:|:--:|
|논리형|Boolean|1 bit|true,false
||
|문자형|Char|2 byte|0 ~ 65,535
||
|정수형|Long|8 byte|-2^63 ~ 2^63 -1
||Int|4 byte|-2^31 ~ 2^31 -1
||Short|2 byte|-2^15 ~ 2^15 -1 (-32,768 ~ 32,767)
||Byte|1 byte|-2^7 ~ 2^7-1 (-128 ~ 127)
||
|실수형|Float|4 byte|약 1.4E-45 - 3.4E+38
||Double|8 byte|약 4.9E-324 - 1.7E+308
<bar>

<bar>

___

## 📚 Template
```kotlin
var name = "hyo-sang"
var lastName = "Seong"
println("my name is ${name}lastName")

println("my name is ${name + lastName}.")

println("my name is ${name}\${lastName}.")

println("my name is ${name}\\lastName")
```

📌자바와의 차이점

- ' + '가 아닌 ' ${내용} ' 을 사용 '{ }'는 띄어쓰기 구분 용도

- 변수 두개가 이어질 경우 ' ${ } '안에서 + 사용 가능

- ' $변수명 '뒤에 ' \ '를 붙이면 변수명뒤로는 문자취급 

- ' $변수명 '뒤에 ' \ '를 문자로 넣고 싶을시, ' 역슬래쉬 두번 '입력

___

## 📚 반복문
<br>

### 📙for, while문
```kotlin

for (변수 in 시작..끝 step 증가량) {

}

for (변수 in 시작 until 끝){ // 끝 미포함  

}

for (변수 in 끝 down 시작 ) {

}

for (변수 in 배열명.indices) { //배열요소 한번에 출력

}

for (변수 in 배열명) { //배열요소 하나씩 출력

}

for ((index : index, name : String) in name.indeces.withIndex()) {

}
```
📌자바와의 차이점

- 표기변경 ' .길이 ' 에서 ' .indices ' 또는 생략

<br>

### 📙when문
<br>

>구문식 (Expresstion)
```kotlin
var jumsu : Int = (count / 10) * 10
when(jumsu) {

100 -> print("1순위")

90, 80, 70 -> print("2순위") //일부 항목지정

in 69..60 -> print("3순위") //범위지정

!in 10..0 -> print("통과")

!is Int -> print("정수가 아님")

}
```
>표현식 (Statement)
```kotlin
var b : Int = when(scope) {
1 -> 1
2 -> 2

else -> 3
}
```
📌자바와의 차이점

- 표기변경 ' switch ' 에서 ' when ' 으로

- 표기변경 ' : ' 에서 ' -> ' 로 

- break 생략

- ' , ' // 일부 항목지정 가능

- " in 시작숫자. .마지막 숫자 " // 범위지정 가능

- ' !in ' // 위 항목의 부정

- ' !is ' // 논리판별

- 표현식 사용 가능

- 표현식의 경우, 예외가 발생하지 않도록 else를 필수로 넣어야 됌

- 표기변경 ' default ' 에서 ' else ' 로
<br>
<br>
  
___

## 📚 Array(배열) and List
<br>

### 📙Array(배열)
<br>

> 1차원 배열
```kotlin
var one = Array<Int>(4,{0})

val array = arrayOf(1,2,3)

val arrayOf = arrayOf(1, "d", 3.14f)

one[0] = 10
one[1] = 20

```


> 2차원 배열
```kotlin
var arr1 = Array(2){Array(3){i->(5)}} //2행 3열 초기화값 5

var arr2 = arrayOf( arrayOf(5,5,5), arrayOf(5,5,5) ) //위와 동일

val arr3 = Array(2){ i -> Array(3){ j ->(i*3) + (j+1)}} // [{1,2,3},{4,5,6}]

var count2 = 0
    for((count1, i) in arr1.indices.withIndex()){
        for(j in arr1[i]){
            println("${count1}행 ${count2}열의 값은 $j 입니다.")
            count2++
        }
        if(count2 == arr1[i].size){
            count2 = 0;
        }
    }
```
📌자바와의 차이점
- val를 쓰는 이유는 주소값을 참조하므로
- 1차원 배열
  - var 배열명 = Array<데이터 타입>(갯수, {초기화값})

  - var 배열명 : IntArray = intArrayOf(1,2,3) //값을 바로 입력
  
  - 데이터 타입 혼용 가능

  - 배열명[인덱스] = 값 입력



- 2차원 배열
  - var 배열명 = Array(행 갯수){ Array(열 갯수), { _->(초기확 값)} }

  - 1차원 배열의 "초기화값"자리에 " 1행에 대한 arrayOf(값), 2행에 대한 arrayOf(값) "를 넣음

  - 자바코드로 바꿔서 이해 할 예정
  
  - java의 확장형 for문으로 값을 출력하는 것과 같음
<br>
<br>
  
### 📙List
<br>

>List
```kotlin
val list1 = listOf(1,"d",11L) 
```

>MutableList(수정가능)
```kotlin
val arraList1 = arrayListOf(1,"d",3)
```
📌List와 mutableList의 차이점
- mutableList인터페이스를 상속받은 ArrayList는 mutableList의 set메소드가 존재하므로 읽기만 가능한 List와는 다르게 쓰기도 가능
<br>
<br>
___

## 📚 Nullable / NonNull
<br>

```kotlin
var nullName : String? = null

val nullNameInUC = nullName.?toUpperCase()

val name = "joyce"
val lastName : String? = null
var fullName = name + (lastName ?: "Hong")

fun igonoreNulls(str: String?){
    val mNotNull: String = str!!

val email: String? = "tjdgytkd!naver.com"
email?.let{
        println("my email is $email")
    }
}


```
📌자바와의 차이점
- 자료형뒤에 ' ? '이 붙지 않을 경우, null 입력이 불가능 

- 메소드 사용시에는 객체명뒤에 ' ? '을 붙이면 null값일시, Skip

- " 객체명?: "는 null값일떄 실행

- " 객체명?.let "는 null값이 아닐떄 실행

- ' !! '는 NonNull로 선언
