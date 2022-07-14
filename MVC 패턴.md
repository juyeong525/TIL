# mvc 패턴

- #### mvc 패턴이란?

  - MVC 패턴은 애플에서 기본적으로 지원하는 디자인 패턴으로, `Model + View + Controller` 구조의 아키텍처 패턴을 말함
    - <span style="color:yellow">Model</span>: 앱의 데이터와 비즈니스 로직을 갖고 있음
    - <span style="color:yellow">View</span>: 사용자에게 데이터를 보여주거나 UI를 담당
    - <span style="color:yellow">Contorller</span>: Model과 View의 중간다리 역할로 View로부터 사용자의 action을 받아 Model에게 어떤 작업을 해야 하는지 알려주거나, Model의 데이터 변화를 View에게 전달하여 View를 어떻게 업데이트할지 알려줌

- MVC 패턴에서 각 영역의 대화
  
  - ![img](https://velog.velcdn.com/images%2Fzooneon%2Fpost%2F9ecc5d4b-f902-4975-9aea-9724aa0ccff2%2Fimage.png)
  - View to Controller
    - Controller는 View에서 발생할 수 있는 action에 대한 **target**을 만들어둔다.
      그래서 View에서 유저의 action이 발생할 경우 Controller에 있는 target이 이를 받아들이고 작업을 수행한다.
  
  - Model to Controller
    - Model은 Observer 패턴( Observer 패턴에 관한 내용은 다른 글에서 따로 정리하도록 하겠다. )의 **Notification**과 **KVO**(Key Value Observation)를 통해 Controller에게 알린다.
      Notification과 KVO는 일을 수행하는 객체(publisher)가 진행하던 작업이 끝나면 자신들을 구독 중인 객체들(subscribers)에게 신호를 보내는 방식이다.
      간단하게 설명하자면, 작업이 완료됐을 때 라디오 센터에서 전파를 보내는 것처럼 Controller에게 신호를 보낸다.
  
