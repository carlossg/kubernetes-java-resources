# Kubernetes Resources to Understand Java

Running

```bash
for d in eclipse-temurin-*; do
	kubectl delete -k $d > /dev/null 2>&1
	kubectl create -k $d
done

# Get the logs
kubectl get pods -l app=java -o go-template='{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}' | 
	sort |
	parallel --tag -j 1 kubectl logs
```

## Output

```
eclipse-temurin-11-1024m-2g-java	VM settings:
eclipse-temurin-11-1024m-2g-java	    Max. Heap Size (Estimated): 512.00M
eclipse-temurin-11-1024m-2g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-11-1024m-2g-java
eclipse-temurin-11-1024m-2g-java	openjdk version "11.0.18" 2023-01-17
eclipse-temurin-11-1024m-2g-java	OpenJDK Runtime Environment Temurin-11.0.18+10 (build 11.0.18+10)
eclipse-temurin-11-1024m-2g-java	OpenJDK 64-Bit Server VM Temurin-11.0.18+10 (build 11.0.18+10, mixed mode, sharing)
eclipse-temurin-11-1024m-2g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-11-1024m-2g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-11-1024m-2g-java	availableProcessors: 2
eclipse-temurin-11-2000m-8g-java	VM settings:
eclipse-temurin-11-2000m-8g-java	    Max. Heap Size (Estimated): 2.00G
eclipse-temurin-11-2000m-8g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-11-2000m-8g-java
eclipse-temurin-11-2000m-8g-java	openjdk version "11.0.18" 2023-01-17
eclipse-temurin-11-2000m-8g-java	OpenJDK Runtime Environment Temurin-11.0.18+10 (build 11.0.18+10)
eclipse-temurin-11-2000m-8g-java	OpenJDK 64-Bit Server VM Temurin-11.0.18+10 (build 11.0.18+10, mixed mode, sharing)
eclipse-temurin-11-2000m-8g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-11-2000m-8g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-11-2000m-8g-java	availableProcessors: 2
eclipse-temurin-11-250m-512m-java	VM settings:
eclipse-temurin-11-250m-512m-java	    Max. Heap Size (Estimated): 123.75M
eclipse-temurin-11-250m-512m-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-11-250m-512m-java
eclipse-temurin-11-250m-512m-java	openjdk version "11.0.18" 2023-01-17
eclipse-temurin-11-250m-512m-java	OpenJDK Runtime Environment Temurin-11.0.18+10 (build 11.0.18+10)
eclipse-temurin-11-250m-512m-java	OpenJDK 64-Bit Server VM Temurin-11.0.18+10 (build 11.0.18+10, mixed mode, sharing)
eclipse-temurin-11-250m-512m-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-11-250m-512m-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-11-250m-512m-java	availableProcessors: 1
eclipse-temurin-11-500m-1g-java	VM settings:
eclipse-temurin-11-500m-1g-java	    Max. Heap Size (Estimated): 247.50M
eclipse-temurin-11-500m-1g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-11-500m-1g-java
eclipse-temurin-11-500m-1g-java	openjdk version "11.0.18" 2023-01-17
eclipse-temurin-11-500m-1g-java	OpenJDK Runtime Environment Temurin-11.0.18+10 (build 11.0.18+10)
eclipse-temurin-11-500m-1g-java	OpenJDK 64-Bit Server VM Temurin-11.0.18+10 (build 11.0.18+10, mixed mode, sharing)
eclipse-temurin-11-500m-1g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-11-500m-1g-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-11-500m-1g-java	availableProcessors: 1
eclipse-temurin-17-1024m-2g-java	VM settings:
eclipse-temurin-17-1024m-2g-java	    Max. Heap Size (Estimated): 512.00M
eclipse-temurin-17-1024m-2g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-17-1024m-2g-java
eclipse-temurin-17-1024m-2g-java	openjdk version "17.0.6" 2023-01-17
eclipse-temurin-17-1024m-2g-java	OpenJDK Runtime Environment Temurin-17.0.6+10 (build 17.0.6+10)
eclipse-temurin-17-1024m-2g-java	OpenJDK 64-Bit Server VM Temurin-17.0.6+10 (build 17.0.6+10, mixed mode, sharing)
eclipse-temurin-17-1024m-2g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-17-1024m-2g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-17-1024m-2g-java	availableProcessors: 2
eclipse-temurin-17-2000m-8g-java	VM settings:
eclipse-temurin-17-2000m-8g-java	    Max. Heap Size (Estimated): 2.00G
eclipse-temurin-17-2000m-8g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-17-2000m-8g-java
eclipse-temurin-17-2000m-8g-java	openjdk version "17.0.6" 2023-01-17
eclipse-temurin-17-2000m-8g-java	OpenJDK Runtime Environment Temurin-17.0.6+10 (build 17.0.6+10)
eclipse-temurin-17-2000m-8g-java	OpenJDK 64-Bit Server VM Temurin-17.0.6+10 (build 17.0.6+10, mixed mode, sharing)
eclipse-temurin-17-2000m-8g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-17-2000m-8g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-17-2000m-8g-java	availableProcessors: 2
eclipse-temurin-17-250m-512m-java	VM settings:
eclipse-temurin-17-250m-512m-java	    Max. Heap Size (Estimated): 123.75M
eclipse-temurin-17-250m-512m-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-17-250m-512m-java
eclipse-temurin-17-250m-512m-java	openjdk version "17.0.6" 2023-01-17
eclipse-temurin-17-250m-512m-java	OpenJDK Runtime Environment Temurin-17.0.6+10 (build 17.0.6+10)
eclipse-temurin-17-250m-512m-java	OpenJDK 64-Bit Server VM Temurin-17.0.6+10 (build 17.0.6+10, mixed mode, sharing)
eclipse-temurin-17-250m-512m-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-17-250m-512m-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-17-250m-512m-java	availableProcessors: 1
eclipse-temurin-17-500m-1g-java	VM settings:
eclipse-temurin-17-500m-1g-java	    Max. Heap Size (Estimated): 247.50M
eclipse-temurin-17-500m-1g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-17-500m-1g-java
eclipse-temurin-17-500m-1g-java	openjdk version "17.0.6" 2023-01-17
eclipse-temurin-17-500m-1g-java	OpenJDK Runtime Environment Temurin-17.0.6+10 (build 17.0.6+10)
eclipse-temurin-17-500m-1g-java	OpenJDK 64-Bit Server VM Temurin-17.0.6+10 (build 17.0.6+10, mixed mode, sharing)
eclipse-temurin-17-500m-1g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-17-500m-1g-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-17-500m-1g-java	availableProcessors: 1
eclipse-temurin-19-1024m-2g-java	VM settings:
eclipse-temurin-19-1024m-2g-java	    Max. Heap Size (Estimated): 512.00M
eclipse-temurin-19-1024m-2g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-19-1024m-2g-java
eclipse-temurin-19-1024m-2g-java	openjdk version "19.0.2" 2023-01-17
eclipse-temurin-19-1024m-2g-java	OpenJDK Runtime Environment Temurin-19.0.2+7 (build 19.0.2+7)
eclipse-temurin-19-1024m-2g-java	OpenJDK 64-Bit Server VM Temurin-19.0.2+7 (build 19.0.2+7, mixed mode, sharing)
eclipse-temurin-19-1024m-2g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-19-1024m-2g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-19-1024m-2g-java	availableProcessors: 2
eclipse-temurin-19-2000m-8g-java	VM settings:
eclipse-temurin-19-2000m-8g-java	    Max. Heap Size (Estimated): 2.00G
eclipse-temurin-19-2000m-8g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-19-2000m-8g-java
eclipse-temurin-19-2000m-8g-java	openjdk version "19.0.2" 2023-01-17
eclipse-temurin-19-2000m-8g-java	OpenJDK Runtime Environment Temurin-19.0.2+7 (build 19.0.2+7)
eclipse-temurin-19-2000m-8g-java	OpenJDK 64-Bit Server VM Temurin-19.0.2+7 (build 19.0.2+7, mixed mode, sharing)
eclipse-temurin-19-2000m-8g-java	     bool UseG1GC                                  = true                                      {product} {ergonomic}
eclipse-temurin-19-2000m-8g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-19-2000m-8g-java	availableProcessors: 2
eclipse-temurin-19-250m-512m-java	VM settings:
eclipse-temurin-19-250m-512m-java	    Max. Heap Size (Estimated): 123.75M
eclipse-temurin-19-250m-512m-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-19-250m-512m-java
eclipse-temurin-19-250m-512m-java	openjdk version "19.0.2" 2023-01-17
eclipse-temurin-19-250m-512m-java	OpenJDK Runtime Environment Temurin-19.0.2+7 (build 19.0.2+7)
eclipse-temurin-19-250m-512m-java	OpenJDK 64-Bit Server VM Temurin-19.0.2+7 (build 19.0.2+7, mixed mode, sharing)
eclipse-temurin-19-250m-512m-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-19-250m-512m-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-19-250m-512m-java	availableProcessors: 1
eclipse-temurin-19-500m-1g-java	VM settings:
eclipse-temurin-19-500m-1g-java	    Max. Heap Size (Estimated): 247.50M
eclipse-temurin-19-500m-1g-java	    Using VM: OpenJDK 64-Bit Server VM
eclipse-temurin-19-500m-1g-java
eclipse-temurin-19-500m-1g-java	openjdk version "19.0.2" 2023-01-17
eclipse-temurin-19-500m-1g-java	OpenJDK Runtime Environment Temurin-19.0.2+7 (build 19.0.2+7)
eclipse-temurin-19-500m-1g-java	OpenJDK 64-Bit Server VM Temurin-19.0.2+7 (build 19.0.2+7, mixed mode, sharing)
eclipse-temurin-19-500m-1g-java	     bool UseMaximumCompactionOnSystemGC           = true                                      {product} {default}
eclipse-temurin-19-500m-1g-java	     bool UseSerialGC                              = true                                      {product} {ergonomic}
eclipse-temurin-19-500m-1g-java	availableProcessors: 1
```