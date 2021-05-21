# newdeploy-broken
- using `spec.runtime.podspec`

Error log from executor pod
```
executor-66c6f5bbc9-kc2k6 executor {"level":"error","ts":"2021-05-21T00:26:24.725Z","logger":"new_deploy","caller":"newdeploy/newdeploymgr.go:432","msg":"error creating k8s resources for function","error":"error creating deployment newdeploy-hellojs-default-9833-3aa5169ca2e3: Deployment.apps \"newdeploy-hellojs-default-9833-3aa5169ca2e3\" is invalid: spec.template.spec.containers[2].image: Required value","errorVerbose":"Deployment.apps \"newdeploy-hellojs-default-9833-3aa5169ca2e3\" is invalid: spec.template.spec.containers[2].image: Required value\nerror creating deployment newdeploy-hellojs-default-9833-3aa5169ca2e3\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).fnCreate\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:494\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).createFunction.func1\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:425\ngithub.com/fission/fission/pkg/throttler.(*Throttler).RunOnce\n\t/go/src/pkg/throttler/throttler.go:215\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).createFunction\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:423\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).initFuncController.func1.1\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:336\nruntime.goexit\n\t/usr/local/go/src/runtime/asm_amd64.s:1337","function_name":"hellojs","function_namespace":"default"}
executor-66c6f5bbc9-kc2k6 executor {"level":"error","ts":"2021-05-21T00:26:24.726Z","logger":"new_deploy","caller":"newdeploy/newdeploymgr.go:338","msg":"error eager creating function","error":"error creating k8s resources for function hellojs_default: error creating deployment newdeploy-hellojs-default-9833-3aa5169ca2e3: Deployment.apps \"newdeploy-hellojs-default-9833-3aa5169ca2e3\" is invalid: spec.template.spec.containers[2].image: Required value","errorVerbose":"Deployment.apps \"newdeploy-hellojs-default-9833-3aa5169ca2e3\" is invalid: spec.template.spec.containers[2].image: Required value\nerror creating deployment newdeploy-hellojs-default-9833-3aa5169ca2e3\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).fnCreate\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:494\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).createFunction.func1\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:425\ngithub.com/fission/fission/pkg/throttler.(*Throttler).RunOnce\n\t/go/src/pkg/throttler/throttler.go:215\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).createFunction\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:423\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).initFuncController.func1.1\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:336\nruntime.goexit\n\t/usr/local/go/src/runtime/asm_amd64.s:1337\nerror creating k8s resources for function hellojs_default\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).createFunction\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:436\ngithub.com/fission/fission/pkg/executor/executortype/newdeploy.(*NewDeploy).initFuncController.func1.1\n\t/go/src/pkg/executor/executortype/newdeploy/newdeploymgr.go:336\nruntime.goexit\n\t/usr/local/go/src/runtime/asm_amd64.s:1337","function":{"metadata":{"name":"hellojs","namespace":"default","selfLink":"/apis/fission.io/v1/namespaces/default/functions/hellojs","uid":"f4d0db5a-6209-4db1-9833-3aa5169ca2e3","resourceVersion":"34300643","generation":1,"creationTimestamp":"2021-05-21T00:26:24Z","annotations":{"fission-name":"podspec-example","fission-uid":"e4d18e20-dc33-4e18-b2ef-eb9fc323a36e"},"managedFields":[{"manager":"fission-bundle","operation":"Update","apiVersion":"fission.io/v1","time":"2021-05-21T00:26:24Z"}]},"spec":{"environment":{"namespace":"default","name":"nodejs"},"package":{"packageref":{"namespace":"default","name":"hellojs-e4485d5e-0752-42ca-8c37-d123655f9f66","resourceversion":"34300629"}},"secrets":null,"configmaps":null,"resources":{"limits":{"cpu":"50m","memory":"128Mi"},"requests":{"cpu":"25m","memory":"64Mi"}},"InvokeStrategy":{"ExecutionStrategy":{"ExecutorType":"newdeploy","MinScale":1,"MaxScale":5,"TargetCPUPercent":30,"SpecializationTimeout":120},"StrategyType":"execution"},"functionTimeout":60,"idletimeout":120,"concurrency":5}}}
executor-66c6f5bbc9-kc2k6 executor {"level":"error","ts":"2021-05-21T00:26:28.319Z","logger":"new_deploy","caller":"newdeploy/newdeploymgr.go:823","msg":"function environment no longer exists","environment":"node12-ts-kq","function":"newdeploy-node-hello-default-9d9e-932d5e8adaab"}
```