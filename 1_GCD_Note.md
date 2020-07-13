Priorities
1. main
2. .global(qos: .userInteractive) -> returns to the mainQueue during the touch gesture, rarely used
3. .global(qos: .userInitiated) -> touching a button, ex) opening a saved document
4. .global(qod: .utility) -> long running tasks with progress indicators, like computations, networking, etc
5. .global(qos: .background) -> for tasks the user is not directly aware of, doesn't at all require user interactions, ex) network activity like prefetching, database maintenanace, synchronizing with remote service or backups. System aims for energy efficiency.
6. .global() //.default qos
7. .global(qos: .unspecified)
8. private queues can be created using DispatchQueue(label:"com.juno.serial") // it is serial by default
9. concurrent queue can be created using DispathQueue(label: "com.juno.worker", qos: .utility, attributes: .concurrent)
10. Serial queue: executes one at a time
11. Concurrent queue: executes multiple at a time
12. Dispatching a task asynchronously: current queue can conitnue immediately with the next task 
13. Dispatching a task synchronously from a serial queue: it must wait until the task completes before it can do anything else
14. Disptaching a task synchronously from a concurrent queue: it can continue working on other tasks on its other threads.
15. Concurrent is not the same as asynchronous. you can run a task synchronously or asynchronously from a serial or concurrent queueon a different serial or concurrent queue.
16. Synchronous versus asynchronous tells you whether the current queue has to wait for the task to complete.
17. Serial versus concurrent just tells you whether a queue has one or more threads. That is whether it can run only one, or many tasks simultaneously. 
18. Synchronous versus asynchronous is about the source of the task. 
19. Serial versus concurrent is about the destination of the task. 
20. Common use case1: Dispatching a non-user interface task asynchronously to a concurrent queue, and dispatching a user interface task asyncrhonously back to the main queue. 
21. Common use case2: Dispatching synchronously to a serial queue to read a shared resource value. And dispatching asynchronously to a serial queue to write a shared resource value. 

