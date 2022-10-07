# Kubernetes Resources to Understand Java

Running

```bash
for d in eclipse-temurin-*; do kubectl delete -k $d; kubectl create -k $d; done
kail -n default --since 2m
```
