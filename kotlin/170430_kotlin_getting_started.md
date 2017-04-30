# Kotlin Getting Started

## Kotlin?
- 코틀린은 IntelliJ 를 만든 JetBrains 에서 만든 JVM 기반의 언어이다.
- Java와 100% 호환성을 가지고 있기 때문에 Java의 대안언어로 각광받고 있으며, 현재 안드로이드, Tomcat, Java EE, Web 를 개발할 때 사용할 수 있다

## 특징
- Null Pointer Expcetion 이 자유롭다
- 자바의 boilerplate 코드 들을 줄여주고 간결하게 코드를 작성할 수 있는 문법을 제공한다
- `==` 연산자는 Java의 `equals()` 와 동일하게 동작한다
    + 자바에서는 `String i` 와 `String j` 를 `==` 으로 비교했을 경우, 가르키는 객체가 다르기 때문에 `False`가 반환된다
    + 여타 다른 언어에서는 `Value` 를 검사하기 떄문에 위의 경우 `True` 를 반환한다
    + Kotlin 에서는 `==` 이 Java의 `equals()` 와 동일하게 동작하기 때문에 위의 경우 `True` 를 반환한다
    + Kotlin 에서 동일한 객체인지 검사하려면 `===` 을 사용하면 된다
- Functional Programming을 지원할 뿐만 아니라, Java 에서의 불편한 점들이 많이 개선되었다
- JetBrains 에서 개발했기 때문에 Andoird Studio 에 Java 에서 Kotlin 으로 변환하는 툴을 제공하고 있다
- Kotlin 은 안드로이드 전용 언어가 아니기 때문에 서버 프로그래밍, 웹 프로그래밍에도 사용할 수 있다

## 설치
1. Kotlin 플러그인 설치
    - [Android Studio] - [Preferences] - [Plugins] - [Install Jetbrains Plugin] - [Kotlin]
2. 프로젝트 변환
    - [Android Studio] - [Tools] - [Kotlin] - [Configure Kotlin in Project]
3. 실행
    - [Android Studio] - [Run] - [Run 'app']

## 참고
- http://kotlinlang.org/docs/tutorials/kotlin-android.html
- https://news.realm.io/kr/news/android-kotlin/
- https://gist.github.com/Hazealign/1bbc586ded1649a8f08f