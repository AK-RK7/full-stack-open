  ```mermaid
    
  sequenceDiagram
    participant user
    participant browser
    participant server

    user->>server: new user input is send to server via browser when the SAVE button is clicked 
    Note right of browser: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: content-type: application/json
    server-->>browser: HTTP status code 201
    deactivate server
    
    Note right of browser: the server does not redirect, the browser stays on the same page, & it sends no further HTTP requests

```