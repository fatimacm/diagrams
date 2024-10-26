
```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    Note right of browser: with the id we will identify the functions
    browser->>server: <form id='notes_form'>
    activate server
    
    Note right of browser: The function that is executed makes the POST request
    browser->>server: sendToServer(note)
    activate server
   
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    deactivate server
    server-->>browser: the JSON format
    deactivate server
    Note right of browser: {"content":"TACO","date":"2024-10-26T04:07:59.019Z"}
