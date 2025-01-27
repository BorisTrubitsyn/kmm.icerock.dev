---
sidebar_position: 2
---

# expect/actual

expect/actual - это механизм, позволяющий использовать в общем коде платформенную реализацию класса, функции или переменной. 
Изучите [раздел](https://kotlinlang.org/docs/mpp-connect-to-apis.html) на официальном сайте.  
В качестве практического задания, предлагаем вам изменить проект, который вы создавали по [инструкции](https://kotlinlang.org/docs/kmm-create-first-app.html) в разделе [Основы Kotlin Multiplatform Mobile](kmm):
- Добавьте в общий код `expect` функцию `log()`
- Добавьте `actual` реализацию функции `log` для Android, используя функцию `Log.d(String tag, String msg)` из пакета `android.util`
- Добавьте `actual` реализацию функции `log` для iOS, используя `NSLog()`
- Протестируйте на обеих платформах

## Добавление зависимостей

Как вы уже знаете из раздела [Основы Kotlin Multiplatform Mobile](kmm), подключить библиотеку можно напрямую к таргету, а с помощью `expect` и `actual` использовать ее в общем коде.

Для практики, выполните следующее задание. Используйте проект, который вы изменяли ранее:
- Подключите [moshi](https://github.com/square/moshi) к Android таргету
- Подключите pod [SwiftyJSON](https://github.com/SwiftyJSON/SwiftyJSON) к iOS приложению
- Добавьте expect функцию `getValueByKeyFromJsonString(jsonString: String, key: String): String`
- Добавьте в общий код константу `jsonStringConst`, проинициализируйте ее любым Json-ом, [сервис для генерации](https://json-generator.com/)
- Для каждой платформы выведите на экран значение какого-нибудь поля
    - Добавьте `actual` реализацию функции `getValueByKeyFromJsonString` для Android используя библиотеку moshi
    - Добавьте `actual` реализацию функции `getValueByKeyFromJsonString` для iOS используя библиотеку SwiftyJSON
    
## typealias 

Чтобы узнать, как можно упросить использование механизма expect/actual, [прочитайте](https://kotlinlang.org/docs/mpp-connect-to-apis.html#rules-for-expected-and-actual-declarations) о возможностях `typealias` и выполните следующие действия, используя проект, который вы изменяли ранее: 

- Создайте `expect class AtomicRef`
- Добавьте `actual` реализацию используя `typealias` и класс `java.util.concurrent.atomic.AtomicReference`
- Добавьте `actual` реализацию для iOS
- Убедитесь в успешной компиляции приложения
