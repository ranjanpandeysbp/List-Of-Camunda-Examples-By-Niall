# List of My Camunda Examples
 This is a list showing the most useful of the examples that I've created. They aim to show common solutions and demonstrate Interesting patterners.

## Generic Error and returned

 An example of throwing a BPMN from any point in the process and returning back to that point after the problem has been resolved.

[Source Code Here](https://github.com/NPDeehan/GenericErrorAndReturn)

 ![Error-Return-Process](https://raw.githubusercontent.com/NPDeehan/GenericErrorAndReturn/master/src/main/resources/genericErrorAndReturn.png)

## Idempotent Camunda Process

A Pattern for creating process that will only start one instance per request. So that if an external system sends multiple identical requests it will not start any new processes if one has been successfully started.

[Source Code Here](https://github.com/NPDeehan/idempotent-process-example)

![idempotent-camunda-process](https://raw.githubusercontent.com/NPDeehan/idempotent-process-example/master/img/complete-process.png)

## Multi-instance Messaging between processes.
This demonstrates a way in which you can asynchronously start lots of instances of another process and be able to wait for each to return with results.

[Source Code Here](https://github.com/NPDeehan/multi-instance-messages)

![message-between-process](https://raw.githubusercontent.com/NPDeehan/multi-instance-messages/master/src/main/resources/image/MessageFlow.png)

## Compensating Multi-Instance Sub processes
When you start lots of sub processes from a parent and then decided you want to shut things down, you need to ``undo`` or ``compensate`` what has already been completed and cancel the  instances that have not yet done anything. This examples show s a nice way of doing that.

[Source Code Here](https://github.com/NPDeehan/CompensateMulti-InstanceSubprocessExample)

![compensate](https://raw.githubusercontent.com/NPDeehan/CompensateMulti-InstanceSubprocessExample/master/screenshots/SubProcessCockpit.png)

## Suspend a process
An example of how a process can be made to suspend itself under a specific condition

[Full Source Code Here](https://github.com/NPDeehan/SusupendInstanceExample)
```Java

        execution.getProcessEngineServices()
                .getRuntimeService()
                .updateProcessInstanceSuspensionState()
                .byProcessInstanceId(execution.getProcessInstanceId())
                .suspend();

```
