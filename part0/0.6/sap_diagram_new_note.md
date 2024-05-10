# Single Page App Diagram - Creating a New Note

The following HTTP exchange occurs as the user loads the website and then enters text on the client browser.

### Sequence diagram of client(browser)-server interaction
```mermaid
sequenceDiagram
participant Client
participant Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
activate Server
Server-->>Client: Returns HTML
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate Server
Server-->>Client: Returns CSS
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
activate Server
Server-->>Client: Returns JavaScript
deactivate Server
Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate Server
Server-->>Client: Returns JSON data of all notes
deactivate Server
Client->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate Server
Server-->>Client: Updates page with new note and returns JSON of all notes including<br /> new note: {"message":"note created"}
deactivate Server
```
