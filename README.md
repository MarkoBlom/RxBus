# RxBus [Deprecated]

This is a simple Rx Event Bus implementation using Kotlin.
Includes small Android example project.

You should think twice though before using an event bus in project, it might create a complicated data flow in your app and a nightmare for debugging later. 
Also Rx is already providing you all event bus capabilities, but offer more control over data flow and scope.

## How to use
```kotlin
//subscribe to events
Bus.observe<ExampleEvent>()
      .subscribe { doSomething() }
      .registerInBus(this) //registers your subscription to unsubscribe it properly later
                
//send events
Bus.send(ExampleEvent(someData))

//unsubscribe from events
Bus.unregister(this)
```

##Gradle
```Groovy
compile 'com.eightbitlab:rxbus:1.0.2'
```

License
-------

    Copyright 2016 Dmitry Saviuk

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
