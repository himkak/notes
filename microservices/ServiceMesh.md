# service mesh:
- Do not burden my code with all these infrastructure related decisions
- Its a dedicated infrastructure layer for making service-to-service communication safe fast and reliable.

## Features provided:
- service discovery : eureka
- canary deploy / rolling deploy
- Distributed Tracing
- security
- multi protocol support

All this is managed by 2 modules: control plane and sidecar

![IMAGE](https://github.com/himkak/notes/blob/master/microservices/ServiceMesh_TrafficControl.PNG)

Sidecar framework is Envoy and control-plane framework is Istio

![IMAGE](https://github.com/himkak/notes/blob/master/microservices/ServiceMesh.PNG)

## Service Mesh Vs Api Gw Capabilities

![IMAGE](https://github.com/himkak/notes/blob/master/microservices/ServiceMesh_Vs_ApiGw_Capabilities.PNG)

# References
https://www.youtube.com/watch?v=QiXK0B9FhO0 
https://www.youtube.com/watch?v=nnxWMhy0mpA
