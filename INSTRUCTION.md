### 1. Create the cluster from config file:
```bash
kind create cluster --config cluster.yml
```

### 2. Taint first and second nodes:
```bash
kubectl taint nodes kind-worker kind-worker2 app=mysql:NoSchedule
```

### 3. Run helm installation:
```bash
./bootstap.sh
```

### 4. Validate deployment, statefulSet and other config by the command below:
```bash
kubectl get all,cm,secret,ing -A
```

You need to check that each pod is healthy and running
