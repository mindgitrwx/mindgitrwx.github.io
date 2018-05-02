---
layout: post
title:  "deeplearning 4j 라이브러리 자체를 인텔리제이를 이용해서 돌려보기. 2 - 테스팅 환경 설정"
date:   2018-05-02 22:13:07 +0900
key: softwareEngineering 
categories: SoftwareEngineering 
---

다음 사진의 순서를 따라간다

처음 썼던 포스트와 가장 큰 차이점은 pom.xml 에서 activebydefalt 를 트루로 바꾸는 내용이다.

처음 인텔리제이를 켤 때 부터 다음과 같이 진행한다. 만약 이미 프로젝트가 켜져 있었다면, File - close project를 누른 다음, 다음 사진들의 과정을 그대로 따라간다. 

![Itellij]({{"/assets/img100.png"}})

![Itellij]({{"/assets/img106.png"}})

![Itellij]({{"/assets/img107.png"}})

![Itellij]({{"/assets/img108.png"}})

다음과 같이 하나하나 체크한다. 

![Itellij]({{"/assets/img109.png"}})

![Itellij]({{"/assets/img110.png"}})

![Itellij]({{"/assets/img111.png"}})

![Itellij]({{"/assets/img112.png"}})

![Itellij]({{"/assets/img113.png"}})

아래의 주소에서 jar 라이브러리 파일을 다운받아 준다.

https://jar-download.com/?detail_search=a%3A%22deeplearning4j-core%22&a=deeplearning4j-core
에 들어가서, Downlaod deeplearning4j-core.jar를 받는다. 압축은 처음에 클론시켰던 dl4j의 폴더에 풀어주는 것이 좋다

deeplearning4j의 의존성 jar 파일들을 프로젝트 폴더에 추가하고 나서는 다음 사진의 과정을 통해 그 jar폴더를  통째로 jar를 class path에 추가한다.  


![Itellij]({{"/assets/img016.png"}})

![Itellij]({{"/assets/img114.png"}})

![Itellij]({{"/assets/img115.png"}})

![Itellij]({{"/assets/img116.png"}})


![Itellij]({{"/assets/img117.png"}})

![Itellij]({{"/assets/img118.png"}})

![Itellij]({{"/assets/img119.png"}})

이제 pom.xml 파일을 프로젝트에서 찾는다. 그 후 id 가 test-nd4j-native 인 곳에서 activeByDefault의 값을 true로 바꿔줘야 한다. 그렇지 않으면 ND4J백엔드와 의존성을 가진 클래스들이 동작하지 않는다. 

![Itellij]({{"/assets/img120.png"}})

왜 추가되어있는지는 정확히 모르겠지만 추상클래스를 implement하지 않은 소스가 있다. 그냥 단순히 implement해도 정상적으로 동작한다.

![Itellij]({{"/assets/img121.png"}})

![Itellij]({{"/assets/img122.png"}})

이제 아무 클래스의 테스트 케이스를 돌려보면 다음과 같이 정상적으로 동작함을 알 수 있다.
![Itellij]({{"/assets/img123.png"}})


[dl4j]: https://deeplearning4j.org/
[https://github.com/mindgitrwx/deeplearning4j]: https://github.com/mindgitrwx/deeplearning4j
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
