```mermaid
@startuml
actor Client_57938 as C_57938
actor Client_32788 as C_32788
actor Controller_5000 as Ctrl_5000
actor Image1_9292 as I_9292
actor Image1_59524 as I_59524
actor Image1_46382 as I_46382

C_57938 -> Ctrl_5000: GET /v3 HTTP/1.1
Ctrl_5000 --> C_57938: HTTP/1.1 200 OK\nJSON (application/json)

C_57938 -> Ctrl_5000: POST /v3/auth/tokens HTTP/1.1\nJSON (application/json)
Ctrl_5000 --> C_57938: HTTP/1.1 201 CREATED\nJSON (application/json)

C_32788 -> I_9292: 32788 > 9292 [SYN] Seq=0
I_9292 --> C_32788: 9292 > 32788 [SYN, ACK] Seq=0

C_32788 -> I_9292: GET / HTTP/1.1
I_9292 --> C_32788: HTTP/1.1 300 Multiple Choices\nJSON (application/json)

C_35368 -> Ctrl_5000: GET / HTTP/1.1
Ctrl_5000 --> C_35368: HTTP/1.1 300 MULTIPLE CHOICES\nJSON (application/json)

I_59524 -> Ctrl_11211: get tokens/...
Ctrl_11211 --> I_59524: END

I_46382 -> Ctrl_3306: 46382 > 3306 [SYN] Seq=0
Ctrl_3306 --> I_46382: 3306 > 46382 [SYN, ACK]

I_46382 -> Ctrl_3306: Request Query { ... }
Ctrl_3306 --> I_46382: Response OK

@enduml
```