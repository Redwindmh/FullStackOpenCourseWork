# Diagram of creating a new note

User enters text on client browser and presses the "Save" button. During this interaction, the following HTTP exchange occurs.

### Sequence diagram of client(browser)-server interaction
```mermaid
sequenceDiagram
participant Client
participant Server
Client->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note <br /> Form Data note: Cheering for all of you!
activate Server
Server-->>Client: URL redirect (code 302)
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
activate Server
Server-->>Client: Returns HTML
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate Server
Server-->>Client: Returns CSS
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
activate Server
Server-->>Client: Returns JavaScript
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate Server
Server-->>Client: Returns JSON data
deactivate Server
```
