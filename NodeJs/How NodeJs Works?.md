The NodeJs Project is made up of 2 major components.
1. V8 - What actually executes our code
2. LibUV - which handles asynchronous tasks 


![[How NodeJs Works? 2024-04-24 17.31.51]]

let's say we have an index.js file and using cmd node index.js we will run the code in it.
the execution steps - 
First thing it does is create/spawns a process and this process works on single thread which we will
call main thread.

### In this main thread following things happen is sequence -
1. A project is initialized
2. top level code is executed, (code we directly write in script file like console.log(), etc. not inside any function or callback)
3. require modules (like require('fs'))
4. Event Callbacks register - events like socket event callbacks like server on close() etc. are registered but not run.
5. lastly an Event loop process is started

with main thread we also have Thread pool that comes within this node process.
### Thread Pool
* this thread pool has threads that can be used.
* what happens is whenever there are CPU intensive tasks we don't to process them in main
* thread but rather in different threads, so we can find these threads from this thread pool.
* By default we have 4 threads provided by the pool, which are sitting idly.
* we can manually define 1024 threads
* the cmd for this is => process.env.UV_THREADPOOL_SIZE

### Start Event loop
so by the last step event loop has started and what this loop does is as soon as it starts 
it will check for all the CPU intensive task and offload them to some threads from thread pool.

### let's see sequence with which  Event loop reads and run.
each step is referred as **phase**  of the event loop
1. Expired Timer Callbacks - callback returned from setTimeout, etc.
2. success call back returned from IO Pooling
3. setImmediate Callbacks
4. Close Callbacks - like server close, etc.
5. check if there are any pending tasks, if yes then start the event loop once again, if not then exit.


![[How NodeJs Works? 2024-04-24 18.35.57]]


### P. S.  Order in which setTimeout and setImmediate timers are executed is non - deterministic, as it is bound by the performance of the process.

### what about promises?
so whenever the event loop phase transitions happen from one phase to another phase like it checks if some promise is completed, if so then event loop will execute it.




