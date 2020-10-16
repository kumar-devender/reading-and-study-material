No hard coding, use constants/configuration values.
Group similar values under an enumeration (enum).
Do not write comments for what you are doing, instead write comments on why you are doing
Specify about any hacks, workaround and temporary fixes. Additionally, mention pending tasks in your to-do comments, which can be tracked easily.
Avoid multiple if/else blocks
Use framework features, wherever possible instead of writing custom code.
Null Checks
Exception Handling
Code Indentation and Formatting
Use of logging instead of syso
Code formatting
Optimize Imports
try to avoid abbreviation
Not All One-Liners
No redundant logic
Look for performance optimization. e.g use stringBuilder instead of string for appending or concatenation
Use switch-case Over Multiple if-else for better readability
Objects Creation in a Loop if possible. Java optimizes memory usage for short-lived objects
create a new object only if required.
Use equals over ==
Avoid exposing constructors of sensitive classes
Prefer builder instead of multiple constructor
Use checked exceptions for recoverable conditions and runtime exceptions for programming errors
Check parameters for validity




Does the code follow OOAD
Avoid dynamic SQL, use prepared statement
Mutability
trade-off
 
* Review your code yourself before asking someone else to review. There are possibility that you will find some improvement yourself.





#### Why not to use Wild card import
* Let say Foo is in package a. And if someone a new class Foo in pakcage b then code compile will fail.
```
import a.*;
import b.*;
...
Foo f;
```
* On wild card import give is better compile time performance. Search java.util.ArrayList is better then searching entire java.util a ArrayList.
 





