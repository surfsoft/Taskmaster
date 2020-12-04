# Taskmaster
Taskmaster is a general purpose task management engine written in Kotlin.
It is licenced under the Apache License, Version 2.0.

# Overview
Taskmaster is (will be) capable of accepting a single task ('simple task'), or a set of tasks (a 'complex task'), which 
it will then execute according to the information provided. Task execution is asynchronous, with the client providing 
either a callback mechanism or a notification contact (e.g. an email address).

For security reasons callbacks can only be made to the domain from which the task was received, and notifications can 
only be sent to pre-registered and verified contacts. 

In the simplest sense a simple task is a description of an HTTP request to be made on the client's behalf and can be 
synchronous or asynchronous:
- Synchronous: the response from the remote service is the 'result' of task execution
- Asynchronous: the immediate response from the remote service indicates only the acceptance (or otherwise) of the task,
the remote service responds via a callback at a later time with the result  

A complex task is a composite of multiple simple tasks together with an execution order. Responses (or parts of 
responses) from earlier tasks can be used as inputs to later tasks. Over time Taskmaster will be able to support more 
complex task definitions, task templates, repeating tasks and other features.  

Initially deployable as a stand-alone REST service, Taskmaster will eventually be capable of being embedded in your own 
software. A public Taskmaster service is also anticipated.  

## Etymology
The TV program Taskmaster was the inspiration for this task management engine since the tasks it passes out for 
execution are arbitrary, as are the sources of those tasks.