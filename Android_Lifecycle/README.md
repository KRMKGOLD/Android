# Android Lifecycle

[참고 1](https://developer.android.com/guide/components/activities/activity-lifecycle), [참고 2](https://re-build.tistory.com/4)

- 액티비티는 컴포넌트 중 하나로, 화면 하나 하나를 의미하며, 이 화면 하나(액티비티)에는 UI가 들어가게 된다.
- 사용자의 액티비티 사용에 따라, 액티비티 인스턴스는 Lifecycle에 따라 전환된다. 즉, 사용자의 행동에 따라 액티비티에 실행, 중지, 재개 등의 상태를 가지고 있다.
- Lifecycle Callbacks

    ![](images/Untitled-09000182-eeca-42ea-b247-3a67ed2066fe.png)

    - onCreate() : Activity Launched, 즉 액티비티 처음 시작 시 호출된다. savedInstanceState를 통해서 이전 상태를 불러오거나, Activity에 필요한 구성 요소를 초기화하며, UI를 정의하는 부분.
    - onRestart() : Activity가 중단되었다가 다시 시작되는 경우에 호출된다.
    - onStart() : Activity가 보이기 직전에 호출된다.
    - onResume() : Activity가 사용자와 상호작용 하기 직전과, 다시 실행될 때(returns to the activity, 즉 액티비티에 복귀될 경우)에 호출된다.
    - onPause() : 다른 Activity가 현 Activity를 가리거나 보이지 않는 경우 호출된다. 사용자가 사용하지 않는 리소스를 해제할 때 사용하면 좋다.
    - onStop() : Activity가 더 이상 화면에 보이지 않을 때 호출된다.
    - onDestory() : Activity가 메모리에서 사라지는 경우 호출, finish() 메소드 또는 메모리 확보를 위해서 Activity를 일시적으로 종료시키는 걸 수 있음. 이 두 가지 경우(finish() / 일시적 종료) 는 isFinishing() 를 통해서 구분할 수 있다.

- Fragment Lifecycle

    ![](images/Untitled-83818054-1e14-4770-b2d8-06e4e4b01658.png)

    - onAttach() : Activity에 Attach되는 순간이나, 독자적으로 활동할 수 없는 상태.
    - onCreate() : Fragment가 Activity에서 호출을 받아 생성되는 시점. Activity와는 달리 UI 작업을 onCreate()에서 할 수 없다. Fragment 생성 시 넘겨주는 리소스 등을 여기서 작업해준다.
    - onCreateView() : View를 만드는 공간, 즉 Fragment에 속한 각종 View나 ViewGroup에 대한 작업을 할 수 있다. (Layout을 Inflater해서 View 작업)
    - onActivityCreated() : Activity가 생성된 후에 실행되는 Fragment Lifecycle Callback. View 변경이 가능하다.
    - onStart() : 유저에게 Fragment를 보이게 설정해준다. 이 상태에서 Activity는 Fragment를 포함하고 있는 상태이므로, 이미 Activity는 Started 인 상태다.
    - onResume() : Fragment가 유저와 상호작용이 가능한 상태.
    - onPause() : 해당 Fragment가 Focus를 가지고 있는 상태가 아니면 실행된다.
    - onStop() : 해당 Fragment가 화면에서 완전히 사라질 때 호출된다. Focus를 onPause()와 달리 가지고 있지는 않으나, Back Stack에 존재할 수 있음, 이 시점에서 데이터를 저장하는 것이 좋다.
    - onDestroyView() : Fragment의 View들이 사라지는 시점(리스소들이 해제되는 시점)
    - onDestroy() : Fragment가 완전히 소멸되기 직전 호출된다.
    - onDetach() : Fragment가 Activity에서 Detach, 즉 연결이 끊기기 직전 호출된다.