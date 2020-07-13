1. GCD: Grand Centeral Dispatch, apple's catchy name for underlying 'lib dispatch library' of C programming language.
2. Major update regarding the GCD took place in swift 3
3. GCD provides 5 global dispatch queues + main queue
4. Queue operates in First in First out, whereas out means start, queues start in an order but queues running on a global queue might finish in a different order. This is becuase global queue are concurrent. 
5. Operations wrap object-oriented convenience around dispatch queues. They are highly reusable. You can specify inputs, outputs, and helper methods. You can cancel and define dependencies on other operations. 
6. Most of the time you add operations to an operation queue, which defaults to running on a global queue, off a main queue.
7. Which to use? GCD is easier to use for simple jobs. Operations make it easier to do complex jobs. 

