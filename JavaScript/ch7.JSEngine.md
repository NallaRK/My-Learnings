## Synchronous? Async? Single - Threaded?

* JavaScript is a single-threaded, synchronous language
* So as JS is single threaded language, if a function takes more time, will cause a web page to become unresponsive.
* Few functions in JavaScript acts asynchronously.
  - `setTimeout(function(){ },1000)`

#### JavaScript basically *synchronous* language, but JS can be executed **asynchronously**:

#### JS Engine consists following components:

* Execution stack
  - Functions invoked by other functions get added to the call stack.
  - When function execution completed, it is removed from stack and the frame below continues executing.
* Browser API
* Function queue
* Event loop
* Micro Task
