# Application Components

[참고 1](https://www.tutorialspoint.com/android/android_application_components.htm) ,[참고 2](https://coding-factory.tistory.com/205)

1. 4대 컴포넌트
    - 4대 컴포넌트는 안드로이드 앱의 필수적인 구성 요소
    - 이런 구성 요소들은 AndroidManifest.xml 과 느슨하게 결합됨.
    - Activity, Service, Broadcast Receiver, Content Provider이 있다

      | Components         | Description                                   |
      | ------------------ | --------------------------------------------- |
      | Activity           | UI 화면을 담당하고 있는 컴포넌트              |
      | Service            | 백그라운드 프로세스를 의미                    |
      | Broadcast Receiver | 다양한 이벤트 / 정보를 받아 반응하는 컴포넌트 |
      | Content Provider   | 데이터를 관리 / 제공하는 데 사용하는 컴포넌트 |

2. Activity
    - UI 화면을 담당하고 있는 컴포넌트

        ```java
        public class MainActivity extends Activity {
        	@Override
        	protected void onCreate(Bundle savedInstanceState) {
            	super.onCreate(savedInstanceState);
            	setContentView(R.layout.activity_main);
        	}
        }
        ```

    - 특징
        1. 모든 어플리케이션은 하나 이상의 Activity를 가지고 있어야 한다.
        2. 두 개 이상의 Activity를 한 번에 Display 할 수 없다.
        3. 다른 어플리케이션의 Activity도 불러 올 수 있다.
        4. Activity 내에는 Fragment를 추가해 화면을 분리시킬 수 있다.

3. Service
    - 백그라운드 프로세스를 의미

        ```java
        public class MyService extends Service {
        }
        ```

    - 특징
        1. 화면이 없이 백그라운드에서 돌아가는 컴포넌트.
        2. 한 번 실행된 서비스는 어플리케이션이 종료되도 계속해서 백그라운드에서 돌아감.
        3. 모든 서비스는 Service 클래스를 상속받아서 사용
        4. Network를 통해서 데이터를 받아올 수 있다.

4. Broadcast Receiver
    - 다양한 이벤트 / 정보를 받아 반응하는 컴포넌트

        ```java
        public class MyReceiver  extends  BroadcastReceiver {
           public void onReceive(context,intent){ }
        }
        ```

    - 특징
        1. 대부분 UI가 없음
        2. 안드로이드 이벤트가 발생하고, 어플리케이션이 알아야 하는 상황이라면 알려준다.
        3. 디바이스의 상황을 감지하고 적절한 작업을 수행함.

5. Content Provider
    - 데이터를 관리 / 제공하는 데 사용하는 컴포넌트

        ```java
        public class MyContentProvider extends  ContentProvider {
           public void onCreate(){ }
        }
        ```

    - 특징
        1. 파일 입출력, SQLite, Web 등을 통해서 데이터를 관리한다.
        2. 다른 어플리케이션의 데이터들도 변경할 수 있다.