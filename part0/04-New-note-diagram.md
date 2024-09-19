  ```mermaid
    
  sequenceDiagram
    participant user
    participant browser
    participant server

    user->>server: new user input is send to server via browser when the SAVE button is clicked 
    Note right of browser: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note right of server: URL redirect
    server-->>browser: HTTP status code 302
    deactivate server
    
    Note left of browser: reloads the Notes page
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [...,{"content": "123", "date": 2024-09-19T09:30:17.952Z"}]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

```