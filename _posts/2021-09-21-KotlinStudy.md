----
layout: single
title: "코틀린 공부중"
----

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

## 📚 반복문
<br>

### 📙when문
>구문식
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
>표현식
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

### 📒1차원 배열
```kotlin
var one = Array<Int>(4,{0})

one[0] = 10
one[1] = 20

var 배열명 : IntArray = intArrayOf(1,2,3) //값을 바로 입력
```


### 📒2차원 배열
```kotlin
var two = Array<IntArray>(3, {IntArray(4)} // 3행 4열
```
📌자바와의 차이점

- var 배열명 = Array<데이터 타입>(갯수, {초기화값})
- 배열명[인덱스] = 값 입력

 - var 배열명 : IntArray = intArrayOf(1,2,3) //값을 바로 입력

- 2차원 배열은 1차원 배열의 "초기화값"자리에 "{데이터타입(갯수)}를 넣음

  - var 배열명 = Array<데이터 타입>(갯수, {데이터타입(갯수)}}

<br>


### 📙for, while문

for (변수 in 시작..끝 step 증가량) {

}

for (변수 in 배열명.indices) { //배열요소 한번에 출력

}

for (변수 in 배열명) { //배열요소 하나씩 출력

}
___

## 📚 Template


📌자바와의 차이점

- ' + '가 아닌 ' ${내용 } ' 을 사용 '{ }'는 띄어쓰기 구분 용도

- ' \ '의 구분은 ' \\ ' 출력시 -> ' \ '만 나오게 됌

- " ${내용}$ "의 구분은 ' \ '를 이용 -> " ${내용}\$ "

___

## 📚 Scope Function (apply, with, let, also, run)


< apply >



< with >


< let >


< also >


< run >

___



