```mermaid
flowchart LR
    A[Time: 114.84938<br>]
    Source: 10.0.20.100:57938] -- Destination: controller:5000 --> B[Protocol: HTTP<br>Info: GET /v3 HTTP/1.1]
    B -- Source port: 5000<br>Info: HTTP/1.1 200 OK , JSON --> A
    C[Time: 118.263083<br>Source: 10.0.20.100:57938] -- Destination: controller:5000 --> D[Protocol: HTTP/JSON<br>Info: POST /v3/auth/tokens HTTP/1.1 , JSON]
    D -- Source port: 5000<br>Info: HTTP/1.1 201 CREATED , JSON --> C
    E[Time: 121.372923<br>Source: 10.0.20.100:32788] -- Destination: image1:9292 --> F[Protocol: TCP<br>Info: SYN]
    F -- Source port: 9292<br>Info: SYN, ACK --> E
    G[Time: 121.377361<br>Source: image1:9292] -- Destination: 10.0.20.100:32788 --> H[Protocol: HTTP/JSON<br>Info: HTTP/1.1 300 Multiple Choices , JSON]
```