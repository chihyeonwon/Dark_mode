# Dark_mode
[Android] 다크 모드 스타일 비활성화 하기

## Night Style
![image](https://github.com/chihyeonwon/Dark_mode/assets/58906858/615c246f-953a-4103-ab89-fe7245aaf8ec)     
안드로이드 앱은 스타일을 지정해줄 때 기본적으로 Day와 Night를 구분하여 작성한다. 이는 라이트 / 다크 모드 지원을 위함이다.       
그러나 필자는 다크모드를 별로 선호하지 않는 탓에 테스트 기기를 항상 라이트 모드로 구동해둔 상태였고, 
테스트할 때 다크모드를 완전히 망각하고 있었던 것이다.    

## 다크 모드 비활성화
꽤나 간단한 방법으로 다크 모드를 비활성화할 수 있다.      
최상위 실행단위인 Application 클래스의 onCreate() 에, 아래와 같은 코드를 기입해준다.       
```kotlin
AppCompatDelegate.setDefaultNightMode(AppCompatDelegate.MODE_NIGHT_NO)
```
만약 이를 진입점 Activity 에 적용하면 여러 번 실행되어 버리기 때문에,     
꼭 최상위 실행단위인 Application 클래스에 추가해주도록 한다.    
최종적인 형태는 다음과 같다.     
```kotlin
override fun onCreate() {
    super.onCreate()
    AppCompatDelegate.setDefaultNightMode(AppCompatDelegate.MODE_NIGHT_NO)
}
```
저렇게만 해주면 다크 모드 활성화 상태에서 앱을 키더라도, Day 스타일이 적용되어 표시된다.    
이 간단한 작업을 안 해주고 출시를 해버린다면 꽤나 많은 사용자들에게 안 좋은 첫인상을 줄 수도 있다🤦🏻‍♂️    

스타일을 나누어 작성하는 것이 기본값인 만큼 앞으로 앱 출시 전에 꼭 조심해야 할 것 같다.      

이후에 다크모드 스타일을 따로 지정해준다.      
