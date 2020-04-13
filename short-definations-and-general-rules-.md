##### Encapsulation
* Encapsulation hides details at the implementation level.
* Encapsulation hides internal working so that you can change it later.
* Expose behavior not data. Object Encapsulate behavior.
* For example, in Java 8, the java.util.HashMap changes its implementation to use a binary tree instead of LinkedList to store objects in the same bucket after a certain threshold.
##### Abstraction
* Abstraction hides details at the design level.
* Abstraction hides complexity by giving you a more abstract picture(generalize view), a sort of 10,000 feet view.
* Coding for interfaces then implementation helps you to write flexible code. Use Map instead of HashMap, Use List instead of ArrayList.
##### Maintainable
* You should be able to change the implementation without changing the client. In another way without changing the client. Class is completely isolation. Your class should not know who is using it.
##### Code fragility
* Tendency of software to break in many places every time it is changed.
##### Code Rigidity
* Every change cascade of subsequent changes in dependent module.
##### Technical debt
* Cost of prioritizing fast delivery over code quality over long period of time.
##### OO Programing
* Using OO language feature.
##### OO Design
* Leveraging OO principle to make your code more effective.
##### Orthogonality
* Changes in one should not force other to change. No hidden side effect.
##### Coherence:
* Every piece of object should focus on solving one problem.
* All method should form a group and should be related to each other in term of what they are doing. 
* Not grab a bag of random stuff like System class in java.
##### Coupling: 
* Two thing are connected with each other in indirect ways. You change one of them and other one have to change.
E.g global variable. You you change one function using global variable there are chances that you have to change the other function which is using the same global variable.
Has side effect
##### Delegation:
* The object that has the information should do the work.
* Ask for help not information. Limit scope of change only at one place.
* Do not get the data and act on it instead ask the object to do thing that contain the data.
##### Clean code
* Maintainable and readable and understandable
* Transparency
* Obvious
* Simplicity

#### How to write Clean code:
* Constant refactoring
* Design patterns
* Unit testing(TDD)
 
#### Benefits lose coupling and high cohesiveness
* Easy to understand
* Transparent
* Easy to Maintain

#### General
* Class name should be noun
* Interfaces should be adjective
* You can not eliminate coupling but we can minimize it.
* Build increment. Big Upfront design are incorrect.
* Reduce coupling so that if we have to change something in an object we do not have to change anything at the usage of that object.
