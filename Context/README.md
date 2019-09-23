# Context

[참고 1,](https://developer.android.com/reference/android/content/Context) [참고 2](https://www.charlezz.com/?p=1080), [참고 3](https://arabiannight.tistory.com/entry/272)

1. Context

   - Docs 정의 : 앱 환경에 대한 전역 정보에 대한 인터페이스. Android 시스템에 의해서 구현되는 클래스이며, 앱 별로 리소스 및 클래스에 대한 접근과 Activity의 실행, 브로드 캐스팅 및 Intent 수신과 같은 애플리케이션 레벨에 대한 호출을 허용합니다.
   - `getPackageName()`, `getResource()`, `startActivity`, `startService`, `getSystemService` 등으로, 시스템 레벨에서 제공하는 정보를 얻을 수 있다.
   - 시스템에 대한 리소스 확인, DB 및 환경 설정에 대한 엑세스 확보 등과 같은 서비스 제공.
   - Activity는 Context 객체를 상속받기 때문에, Activity는 특정 자원, 클래스, 앱 환경 정보에 대해 접근할 수 있게 제공한다.

2. 왜 Context를 통해서**만** 가능한가?

   → C# vs Java 안드로이드 애플리케이션 비교

   ```C#
    //Get an Application Name.
     String applicationName = System.AppDomain.CurrentDomain.FriendlyName;
    
    //Start a new process(application)
     System.Diagnostics.Process.Start("test.exe");
   ```

   ```Java
    //Get an application name
    String applicationName = this.getPackageName();
    
    //Start a new activity(application)
    this.startActivity(new Intent(this, Test.class));
   ```

   

   - C#에서는 System이라는 정적변수를 통해서 애플리케이션 이름을 가져왔으나, 안드로이드에서는 this, 즉 Context에 정의된 인스턴스 함수를(여기서는 `getPackageName()`) 이용해야만 한다
   - 이러한 차이점이 발생하게 된 까닭 : 안드로이드 플랫폼은 __정말 다양한 상황__에서 사용되고 있고, 어플리케이션들은 프로세스와 달리 별도로 관리되어, OS 커널이 아닌 `ActivityManagerService`에서 작동되고 있기 때문에 `ActivityManagerService`에 접근해 야만 Android 시스템에 접근이 가능하기 때문.