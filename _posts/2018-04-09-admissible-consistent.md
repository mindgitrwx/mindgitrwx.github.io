---
layout: post
title:  "휴리스틱이 consistent하면 반드시 admissible함을 증명하기"
date:   2018-04-09 04:02:07 +0900
key: AI
categories: AI 
---

이 증명을 하기 전에 알아야 하는 것들

admissible 

consistent

inductive proof 기법을 이용하여 휴리스틱이 consistent하면 반드시 admissible 하다는 것을 증명하자

영어로 된 솔루션 사이트

https://rniwa.com/2009-09-06/proof-every-consistent-heuristic-is-also-admissible/

먼저 해야 할 것. 질문 만들기  

빈칸을 채워보자 

-consistent 는 무엇인가?

-admissible 은 무엇인가?

-증명을 할 때 두 부분을 어떻게 배치시켜야 하는가?

c(x,y): x상태에서 y 상태로 가는 것

consistent - h(x) <= c(x,y) + h(y)

admissible h(x) <= p(x) 임을 보여주는 것

x 로부터 ~ 까지 없다고 가는정

그 경우에 ( ) 는 무한하며 어떤 h(x) 에 대해서도 (        ) 임이 만족된다

x 로부터 ~ 까지 있다고 가정

중간 경유 node에 대한 정의가 필요하다

x에서 g 까지 가는 shortest path는  (                     ) 이다.

---------------------------------------------------------------------------------------------------------------------------

h(x) 를 어떤  consistent heuristic 이라고 하고, c(x,y)를 
x 상태에서 y 상태로 가는 비용이라고 가정하자.

ㄱ. consistent의 가정에 의해 h(x) <= c(x,y) + h(y) 이다.

h가 admissible함을 보여주기 위해, 우리는 p가 x의 경로 비용일 때

h(x) <= p(x) 임을 보여야 한다.

x로부터 goal state 까지 가는 경로가 없다고 가정하자

그 경우에, p(x) 는 무한하며, 어떤 h(x) 에 대해서도 h(x) <= p(x) 임이 만족된다

이제 x 에서 goal state까지 가는 경로가 있다고 가정하자.

중간 경유 node들을 w1, w2..... wn으로 부르기로 한다.

따라서, x에서 g까지 가는 shortest path는 (x, w1, w2, ... wn, g). 이다

    h(g)= 0 이기 때문에 h(Wn) <= c(Wn, g) + h(g) = c(Wn, g) ( ㄱ의 가정에 의해 )

    h(Wn-1) <= c(Wn-1, Wn) + h(Wn) <= c(Wn-1, Wn) + c(Wn). ( ㄴ의 가정에 의해  )

    귀납법을 이용하면

    1과 n-1 사이에 어떤 k라도 다음을 만족하게 된다

    h(wk) <= c(Wk, Wk+1)+....+c(Wn-1, Wn) + c(Wn, g)

그런데, (x, w1, w2, ... wn, g) 가 shortest path 이므로

p(wk) =  c(wk, wk+1) + ... + c(wn-1, wn) + c(wn, g)

따라서 h(wk) <= p(wk) 를 만족한다.

Q.E.D
