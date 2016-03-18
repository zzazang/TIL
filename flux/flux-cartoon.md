# Flux 란?

출처 : http://bestalign.github.io/2015/10/06/cartoon-guide-to-flux/

### Model-View 구조의 문제점

Model 다수와 View 다수 간의 복잡한 데이터 흐름을 단방향으로 바꾸고자 함

![](http://bestalign.github.io/2015/10/06/cartoon-guide-to-flux/04.png)

뷰(view)가 모델(model)을 업데이트하고, 모델이 다른 모델을 업데이트한다. 점점 아주 긴장감 넘치는 Pong 게임처럼 보이기 시작한다.

### 기본 컨셉

![](http://bestalign.github.io/2015/10/06/cartoon-guide-to-flux/05.png)

1. 액션 생성자(the action creator)
  * 모든 변경사항과 사용자와의 상호작용이 거쳐가야 하는 액션의 생성을 담당하고 있다. 언제든 애플리케이션의 상태를 변경하거나 뷰를 업데이트하고 싶다면 액션을 생성해야만 한다.
  * 액션 생성자가 하는 일은 마치 전보기사(telegraph operator)와 같다. 무슨 메시지를 보낼지 알려주면 액션 생성자는 나머지 시스템이 이해할 수 있는 포맷으로 바꿔준다 – [전보기사가 알파벳을 기계들이 처리할 수 있는 모스부호로 바꾸는 것처럼].
2. 디스패쳐(dispatcher)
  * 디스패쳐는 기본적으로 콜백(callback)이 등록되어있는 곳이다. 
  * 액션을 보낼 필요가 있는 모든 스토어(store)를 가지고 있고, 액션 생성자로부터 액션이 넘어오면 여러 스토어에 액션을 보낸다.
  * 만약 스토어들 사이에 의존성(dependency)이 있어서 하나를 다른 것보다 먼저 업데이트를 해야한다면, waitFor()를 사용해서 디스패쳐가 적절히 처리하도록 할 수 있다.
3. 스토어(store)
  * 모든 상태 변경은 반드시 스토어에 의해서 결정되어야만 하며, 상태 변경을 위한 요청을 스토어에 직접 보낼 순 없다. 
  * 만약 스토어가 디스패쳐에 등록되어 있다면, 모든 액션을 받게 될 것이다. 스토어의 내부에서는 보통 switch statement를 사용해서 처리할 액션과 무시할 액션을 결정하게 된다. 만약 처리가 필요한 액션이라면, 주어진 액션에 따라서 무엇을 할 지 결정하고 상태를 변경하게 된다.
  * 일단 스토어에 상태 변경을 완료하고 나면, 변경 이벤트(change event)를 내보낸다. 이 이벤트는 컨트롤러 뷰(the controller view)에 상태가 변경했다는 것을 알려주게 된다.
4. 컨트롤러 뷰(the controller view)와 뷰(the view)
  * 상태를 가져오고 유저에게 보여주고 입력받을 화면을 렌더링하는 역할
  * 뷰는 발표자와 같다. 애플리케이션 내부에 대해서는 아는 것이 없지만, 받은 데이터를 처리해서 사람들이 이해할 수 있는 포맷(HTML)으로 어떻게 바꾸는지 알고 있다.
  * 컨트롤러 뷰는 스토어와 뷰 사이의 중간관리자같은 역할을 한다. 상태가 변경되었을 때 스토어가 그 사실을 컨트롤러 뷰에게 알려주면, 컨트롤러 뷰는 자신의 아래에 있는 모든 뷰에게 새로운 상태를 넘겨준다.

자세한 동작 설명은 http://bestalign.github.io/2015/10/06/cartoon-guide-to-flux/ 에서...

