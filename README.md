# ansible-awx-kubernetes

This will deploy Ansible's upstream Tower project, AWX, as a distributed deployment in Kubernetes. 

## Deploy 

```
git clone https://github.com/rossedman/ansible-awx-kubernetes.git
cd ansible-aws-kubernetes
kubectl apply -f .
```

After this is done deploying it takes awhile to spin up. The best way to tell when its done is by tailing the `awx-task` file and watching for this entry

```
kubectl logs -f awx-web-<some_id>

(InteractiveConsole)

>>> <User: admin>
>>> Default organization added.
Demo Credential, Inventory, and Job Template added.
Successfully registered instance awx-task-1954310302-q6p24
(changed: True)
Creating instance group tower
Added instance awx-task-1954310302-q6p24 to tower
(changed: True)
2017-09-08 22:09:16,456 WARN For [program:awx-celeryd-beat], redirect_stderr=true but stderr_logfile has also been set to a filename, the filename has been ignored
2017-09-08 22:09:16,463 INFO RPC interface 'supervisor' initialized
2017-09-08 22:09:16,463 CRIT Server 'unix_http_server' running without any HTTP authentication checking
2017-09-08 22:0
```

