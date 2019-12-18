Reactive programming
====================

From wikipedia:
---------------
https://en.wikipedia.org/wiki/Reactive_programming

In computing, reactive programming is a declarative programming paradigm concerned with data streams and the propagation of change.With this paradigm it is possible to express static (e.g., arrays) or dynamic (e.g., event emitters) data streams with ease, and also communicate that an inferred dependency within the associated execution model exists, which facilitates the automatic propagation of the changed data flow.

For example, in an imperative programming setting, a := b + c would mean that a is being assigned the result of b + c in the instant the expression is evaluated, and later, the values of b and c can be changed with no effect on the value of a. On the other hand, in reactive programming, the value of a is automatically updated whenever the values of b or c change, without the program having to re-execute the statement a := b + c to determine the presently assigned value of a.

Reactive programming has been proposed as a way to simplify the creation of interactive user interfaces and near-real-time system animation.

For example, in a model–view–controller (MVC) architecture, reactive programming can facilitate changes in an underlying model that are reflected automatically in an associated view.

Other definition:
-----------------
(from: https://medium.com/exploring-code/what-is-reactive-programming-da37c1611382)

In simple words, In Rx programming data flows emitted by one component and the underlying structure provided by the Rx libraries will propagate those changes to another component those are registered to receive those data changes. Long story short: Rx is made up of three key points.


> RX = OBSERVABLE + OBSERVER + SCHEDULERS

Where:
#### Observable: 
Observable are nothing but the data streams. Observable packs the data that can be passed around from one thread to another thread. They basically **```emit the data```** periodically or only once in their life cycle based on their configurations. There are various operators that can help observer to emit some specific data based on certain events, but we will look into them in upcoming parts. For now, you can think observables as suppliers. They process and supply the data to other components.

#### Observers:
Observers **```consumes the data```** stream emitted by the observable. Observers subscribe to the observable using subscribeOn() method to receive the data emitted by the observable. Whenever the observable emits the data all the registered observer receives the data in onNext() callback. Here they can perform various operations like parsing the JSON response or updating the UI. If there is an error thrown from observable, the observer will receive it in onError().

#### Schedulers:
Remember that Rx is for asynchronous programming and we need a thread management. There is where schedules come into the picture. Schedulers are the component in Rx that tells observable and observers, on which thread they should run. You can use ```observeOn()``` method to tell observers, on which thread you should observe. Also, you can use ```scheduleOn()``` to tell the observable, on which thread you should run. There are main default threads are provided in RxJava like ```Schedulers.newThread()``` will create new background that. ```Schedulers.io()``` will execute the code on IO thread.


### Resources:
-------------
* [The introduction to Reactive Programming you've been missing]( https://gist.github.com/staltz/868e7e9bc2a7b8c1f754
).
* [Hot vs Cold Observables](https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339)