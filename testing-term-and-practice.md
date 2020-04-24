### Stub, Mock, and Spy
#### Stub
* Stubbing is the act of making collaborators respond to method calls in a certain way. When stubbing a method, you don’t care if and how many times the method is going to be called; you just want it to return some value, or perform some side effect, whenever it gets called.
* ``` subscriber.receive(_) >> "ok" // subscriber is a Stub() ```
* Compared to a mocked interaction, a stubbed interaction has no cardinality on the left end.

#### Mock
* Mocking is the act of describing (mandatory) interactions between the object under specification and its collaborators.
* ``` 1 * subscriber.receive("message1") >> "ok" // subscriber is a Mock() ```
#### Spy
* A spy is always based on a real object. Hence you must provide a class type rather than an interface type, along with any constructor arguments for the type.
* Method calls on a spy are automatically delegated to the real object.
* After creating a spy, you can listen in on the conversation between the caller and the real object underlying the spy.
* When stubbing a method on a spy, the real method no longer gets called. ``` subscriber.receive(_) >> "ok" ```. Instead of calling SubscriberImpl.receive, the receive method will now simply return "ok"

