# Running `TestSuite`

To run your tests suites pass `testsuites run` command with test name to your `kubectl testkube` plugin. TestSuites are started asynchronously by default.

```sh
kubectl testkube testsuites run test-example

████████ ███████ ███████ ████████ ██   ██ ██    ██ ██████  ███████ 
   ██    ██      ██         ██    ██  ██  ██    ██ ██   ██ ██      
   ██    █████   ███████    ██    █████   ██    ██ ██████  █████   
   ██    ██           ██    ██    ██  ██  ██    ██ ██   ██ ██      
   ██    ███████ ███████    ██    ██   ██  ██████  ██████  ███████ 
                                           /tɛst kjub/ by Kubeshop


Name: test-example.fairly-humble-tick
Status: pending

  STEP | STATUS | ID | ERROR  
+------+--------+----+-------+



Use following command to get test execution details:
$ kubectl testkube testsuites execution 61e1136165e59a3183465125


Use following command to get test execution details:
$ kubectl testkube testsuites watch 61e1136165e59a3183465125
```

After test start you can check current test status with `tests execution EXECUTION_ID` 


# Running tests synchronously 

You can also start test synchronously by passing `-f` flag (like --follow) to your command

```sh
kubectl testkube testsuites run test-example -f

████████ ███████ ███████ ████████ ██   ██ ██    ██ ██████  ███████ 
   ██    ██      ██         ██    ██  ██  ██    ██ ██   ██ ██      
   ██    █████   ███████    ██    █████   ██    ██ ██████  █████   
   ██    ██           ██    ██    ██  ██  ██    ██ ██   ██ ██      
   ██    ███████ ███████    ██    ██   ██  ██████  ██████  ███████ 
                                           /tɛst kjub/ by Kubeshop


Name: test-example.equally-enabled-heron
Status: pending

  STEP | STATUS | ID | ERROR  
+------+--------+----+-------+

...


             STEP            | STATUS  |            ID            | ERROR  
+----------------------------+---------+--------------------------+-------+
  run test: testkube/test1 | success | 61e1142465e59a318346512d |        


Name: test-example.equally-enabled-heron
Status: pending

             STEP            | STATUS  |            ID            | ERROR  
+----------------------------+---------+--------------------------+-------+
  run test: testkube/test1 | success | 61e1142465e59a318346512d |        
  delay 2000ms               | success |                          |        


...


Name: test-example.equally-enabled-heron
Status: success

             STEP            | STATUS  |            ID            | ERROR  
+----------------------------+---------+--------------------------+-------+
  run test: testkube/test1 | success | 61e1142465e59a318346512d |        
  delay 2000ms               | success |                          |        
  run test: testkube/test1 | success | 61e1142a65e59a318346512f |        



Use following command to get test execution details:
$ kubectl testkube testsuites execution 61e1142465e59a318346512b

```