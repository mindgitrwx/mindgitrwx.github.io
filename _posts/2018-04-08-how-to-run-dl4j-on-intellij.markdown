---
layout: post
title:  "deeplearning 4j 라이브러리 자체를 인텔리제이를 이용해서 돌려보기. 1 - 설치 과정 "
date:   2018-04-08 22:13:07 +0900
comments: true
categories: SoftwareEngineering 
---

Deeplearning4J 라는  거대한 프로젝트를 리팩토링해보는 것을 이번 학기의 주제로 잡았다. [dl4j] 로 불리는 이 프로젝트는 텐서플로우와 유사한 딥러닝 프레임워크인데 , 코드의 상태도 좋지 못해 보였고, 그 코드에 딸려 있는 주석의 상태도 좋지 않았다.

IDE나 에디터를 통해서 프로젝트 전체 탐색을 이용, Todo를 검색하면 아직 해야할 일이 많이 남아있었다.

deepleanring4J example 도 아니고 쌩 deeplearning4J 를 리팩토링하는거라 많은 난항이 예상되지만 그래도 얼마 안되는 테스트 케이스를 추가 할 수 있었다.

다음 과정들은 그 테스트 케이스를 추가하기 전 까지의 intelliJ의 환경설정 과정이다.

처음에 인텔리제이가 돈을 지불해야 쓸 수 있는 거라고 알고 있어서 불안했는데, 

자바 프로젝트를 돌릴 때는 Community Edition 으로 충분했다.
화살표의 다운로드를 누르고 다음과 같이 진행해 나가면 된다. 

![Itellij]({{"/assets/img002.png"}})


Space 용량이 많은 디스크로 경로를 바꿔서 설치해준다 


![Itellij]({{"/assets/img003.png"}})


다음과 같이 체크를 하고 설치를 진행한다. 설치가 끝나고 나서 처음 실행하면, 여러 플러그인들을 설치하라고 할 것이다.
Vim에 익숙할시 Vim을 체크해주고, 아니면 체크를 안하고 넘어가주면 된다.


![Itellij]({{"/assets/img004.png"}})


이제 사진과 같은 방식으로 git에서 Dl4j를 클론할 차례다.


![Itellij]({{"/assets/img005.png"}})


밑의 주소는 다음과 같다. 주소를 복사해서 사진처럼 붙여준다.
[https://github.com/mindgitrwx/deeplearning4j]


![Itellij]({{"/assets/img006.png"}})

![Itellij]({{"/assets/img008.png"}})


큰 프로젝트라 시간이 좀 걸릴 것이다. 인텔리제이의 하단 바에 진행상황이 보인다. 


![Itellij]({{"/assets/img009.png"}})


maven 프레임워크를 적용시켜야 한다. 왼쪽의 프로젝트 창에서, 제일 상위 폴더에 오른쪽 클릭한 뒤 다음 과정을 따라간다. 


![Itellij]({{"/assets/img010.png"}})

![Itellij]({{"/assets/img011.png"}})

![Itellij]({{"/assets/img012.png"}})

프로젝트 파일을 파고들어갔을 때, Project SDK is not defined 문구가 아래 처럼 뜨면 setup sdk 를 눌러준 다음, 시키는 대로 한다. jdk, jre가 깔려있으면 잘 진행된다.

![Itellij]({{"/assets/img015.png"}})

https://jar-download.com/?detail_search=a%3A%22deeplearning4j-core%22&a=deeplearning4j-core
에 들어가서, Downlaod deeplearning4j-core.jar를 받는다. 압축은 처음에 클론시켰던 dl4j의 폴더에 풀어주는 것이 좋다

![Itellij]({{"/assets/img016.png"}})

![Itellij]({{"/assets/img017.png"}})


받았던 jar파일을 아래 사진과 같은 과정을 따라가 라이브러리로 만든다. 
오른쪽 버튼을 클릭하면 `Add as Libarary...` 라는 버튼이 나올 텐데, 그걸 클릭하면 Create Library 창이 뜰 것이다.


![Itellij]({{"/assets/img025.png"}})
![Itellij]({{"/assets/img022.png"}})


그러고 나서도 프로젝트를 실행시키면 오류가 3개정도 뜰 텐데, 바로 다음 사진에 나오는 오류는 implement해주고, (Deprecated가 아님), 마지막 오류줄은 그냥 지워버려도 무관하다.


![Itellij]({{"/assets/img023.png"}})
![Itellij]({{"/assets/img024.png"}})


이 과정을 거치면, 이 라이브러리 전체를 테스팅하는데는 문제가 없을 것으로 보인다. 이 테스팅 한 것들을 토대로, 앞으로 하게 될 리팩토링을 진행한다. 


[dl4j]: https://deeplearning4j.org/
[https://github.com/mindgitrwx/deeplearning4j]: https://github.com/mindgitrwx/deeplearning4j
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
