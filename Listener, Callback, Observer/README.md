# Listener, Callback, Observer

[참고](https://www.charlezz.com/?p=768), [참고2](http://blog.naver.com/PostView.nhn?blogId=2hyoin&logNo=220398943180)

1. Caller과 Callee
    - Caller : 호출자, 호출하는 함수를 의미
    - Callee : 피호출자, 호출받는 함수를 의미

    → Caller가 Callee를 호출해 함수의 기능을 수행

    - Callback : Call을 거꾸로(back) 하는 것, 즉 Callee가 Caller를 부르는 방식
        - 시스템 측에서 이벤트를 발생시켜 이에 대한 처리를 요청하는 과정에서 사용됨.
        - 특정 조건이 만족되는 경우 기능을 호출하기 때문에 효율적으로 기능을 수행할 수 있다.
    - Callback Function : 이벤트의 발생을 감지하기 위한 처리와 그 이벤트가 일어났을 때, 실해오딜 각각의 처리를 나누어 코딩할 수 있음.
        - 프로그래머가 사용하는 것이 아닌, 이벤트, 메시지, 알람을 받았을 때 등 어떤 조건을 만족한 경우 자동으로 실행되는 함수.
2. Listener : 특정 이벤트를 처리하는 인터페이스
    - 이벤트가 발생하면 연결된 Listener에게 이벤트를 전달한다.
3. Observer : 데이터나 속성의 변경을 감지하여, 구독자에게 변경사항을 전달함.
4. Callback vs Listener vs Observer?
    - 모두 구현은 인터페이스를 통해서 구현하기 때문에 개발 시에는 비슷한 코드 모형이 나타남.
    - 모두 이벤트를 통지하는 공통점을 가지고 있음
    - Callback은 특정 View 안에 있는 메서드처럼 활동하기 때문에 이벤트 발생 대상이 누구인지 정해져 있으나, Listener는 여러 위젯에 의해서 공유되는 경우가 있기 때문에 발생시킨 대상 View가 누구인지 전달 받아야한다.
    - Listener는 이벤트 발생 시에 사용하고, Observer는 데이터의 변경을 감지하기 위해서 사용하는 개념.