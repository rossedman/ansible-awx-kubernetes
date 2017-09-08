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
```

