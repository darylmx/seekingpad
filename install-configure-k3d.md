
### Create new cluster
`k3d cluster create cluster-dev`
> this creates a cluster server node

### Add agent to cluster
```
k3d node create cluster-dev-agent0 -c cluster-dev
k3d node create cluster-dev-agent1 -c cluster-dev
k3d node create cluster-dev-agent2 -c cluster-dev
```

### Create a new kubeconfig file after cluster creation

`k3d kubeconfig write cluster-dev`
>Note: this will create (or update) the file $HOME/.k3d/kubeconfig-cluster-dev.yaml
Tip: Use it: export KUBECONFIG=$(k3d kubeconfig write mycluster)
Note 2: alternatively you can use k3d kubeconfig get cluster-dev > some-file.yaml
Update your default kubeconfig upon cluster creation (DEFAULT)

`k3d cluster create cluster-dev --kubeconfig-update-default`
>Note: this won’t switch the current-context (append --kubeconfig-switch-context to do so)
Update your default kubeconfig after cluster creation

`k3d kubeconfig merge cluster-dev --kubeconfig-merge-default`
>Note: this won’t switch the current-context (append --kubeconfig-switch-context to do so)
Update a different kubeconfig after cluster creation

`k3d kubeconfig merge cluster-dev --output some/other/file.yaml`
>Note: this won’t switch the current-context
The file will be created if it doesn’t exist
