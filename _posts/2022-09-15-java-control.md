---
layout: single
title:  "[Java] control 조건문"
categories:
  - java
---

### if ~ else if ~ else 조건문

#### 형식
1) if(조건식){실행문} else(아니면){실행문}  
2) if(조건식){실행문} else if(조건식){실행문} else(아니면){실행문}
> else 전까지 else if를 사용하여 계속 조건을 만들수 있다.

#### 예시 소스
```java
int num = 20;

if(num>0) {
  System.out.println("양수");
}else if(num<0) {
  System.out.println("음수");
}else {
  System.out.println("0");
}

double avg = 77.4;

if(avg >= 90) {
  System.out.println("A");
}else if(avg >= 80) {
  System.out.println("B");
}else if(avg >= 70) {
  System.out.println("C");
}else if(avg >= 60) {
  System.out.println("D");
}else {
  System.out.println("F");
}
```
