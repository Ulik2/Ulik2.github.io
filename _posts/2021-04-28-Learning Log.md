---
layout: post
title:  "2021.04.28. Learning Log"
---

# Keywords
  
- 연결리스트  
- 연결리스트 사용 장점  
- realloc  
- malloc의 이해  
- 재귀의 다시이해  
- 연결리스트의 활용: 트리  
(이진 검색 트리)
 
 
 
# 깨달은점 및 주의점

1. malloc은 예전에 썼던 보조바퀴 get_string함수처럼 retrun값을 주는 함수이다. 그 리턴값은 malloc으로 할당한 메모리의 주소가 리턴되기 때문에, 주소를 나타내는 형식자인 pointer로 받아야한다.  
- 오늘 한참 고민했던 것
: 왜 int *p = malloc(sizof(int))이지?  
 int p = malloc(sizeof(int))는  안될까?  
-> 주소를 리턴하니까 당연히 포인터 자료형이지, 그냥 정수인 p면 p의 값에 주소를 넣는 것이니까.

2. malloc관련 잊지 말아야 할 것!  
  - malloc으로 list에 리턴값을 준 이후   
if( list == NULL)  
{  
    return 1;  
}  
즉, 포인터의 작동 확인하는 것을 생활화하자  
  
- malloc으로 heap에 메모리를 할당한 후 free함수를 통해 그 메모리 지정을 풀어주는 것을 잊지말자
(메모리 누수의 원인이 된다.)

3. 이미 형성된 연결리스트에 하나의 요소를 추가하고 싶을때, 기존의 요소에 포인터가 끊기지 않게 해라  
ex) list를 1에 먼저 연결(x)  
      1을 2에 먼저 연결한 후 list를 1에 연결(o)  
why? 2에 연결이 끊기는 순간 2뒤에 요소들은 모두 메모리 누수가 된다.

4. 연결리스트의 장단점
  - 장점: 그냥 배열에 비해서 역동적이다
  = 기존 비열은 요소를 추가하기 위해서 일일이 다 른 요소들의 수정이 필요했지만,
  연결리스트는 다른 요소들의 수정이 없어도 가능하며 변화에 있어서 역동적이고 효율적이다.  
  
  - 단점: 임의적 접근이 비효율적이다.
  = 만약 배열은 특정부분에 접근한다고 가정했을 때, 기존의 배열은 컴퓨터가 바로 접근이 가능했지만
  연결리스트는 그 지점을 찾기위해 처음부터 탐색해야 한다. 즉, 비효율적이다.  
  
연결리스트는 검색, 값 추가에서 배열의 스케일인 n번을 할 수 있으므로 O(n)이다.  
(realloc안해도 되서 더 빠를줄 알았는데..)  
  
반면 배열은 임의적 접근이 가능하며 (정렬이 된) 이진 검색으로는 O(log n)이다.

5. 의문점: 재귀로 함수를 설정할 때 중간에 재귀함수를 넣으면 실행하던 함수가 다 실행을 마치고 재귀함수를 실행하는 것인거 맞을까?
(재귀에 관련해서 더 알아보기)
  
  
  
# 소감과 메타인지
  
한 가지 문제점을 발견했다. 그것은 내가 마음이 급해 진도나가는 것에 급급하고 이전에 배운 내용을 완전히 체득하는 것에 소홀히 했다는 점이다. 
복습의 중요성을 잊지말자. 무작정 진도만 나가는 것을 추구하다가 겉핥기식이 될 수 있다. 좀 더 여유를 가지고 내것으로 만들어버리자.  
수면시간을 줄이고 공부를 하다보니 집중력이 흐트러질 때가 있는 것 같다. 이에 대해서는 적당한 대책을 세워보자. 조금 더 실험이 필요하다.  
(줄어든 수면시간에 적응이 될 것인가? 아니면 이 상태가 지속될 것인가?)
시간관리가 여전히 부족하다. 시간을 좀 더 효율적으로 쓰고 낭비하는 시간을 조금 줄이자.(휴식도 중요한 것이니 가끔은 산책도하고 그러자)  
  
소감만큼은 좀 가볍게 써야겠다 ㅋㅋ 오늘도 무사히 공부를 끝냈다. 공부를 할수록 확실히 내용은 어려워진다 ㅎㅎ.. C언어가 괜히 어렵다고 하는게 아니었어..  
그런데 어려운만큼 성취감도 굉장히 크다. 어렵다고 느끼는 내용을 이해하거나 C로 간단한 코딩을 해서 에러가 덜 뜨면 기분이 좋다! 그리고 잔실수도 많이 줄었다 ㅎㅎ  
지금처럼 목표의식을 가지고 차근차근하자. 그리고 지금처럼 앞으로 코딩을 꾸준히 즐겨나가자!