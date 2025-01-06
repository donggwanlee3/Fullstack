sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks Save
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note with note data
    activate server
    server-->>browser: 201 Created
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Updated notes as JSON
    deactivate server

    Note right of browser: The browser updates the view with the new note

sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser executes JavaScript and fetches notes data

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: Notes as JSON
    deactivate server

    Note right of browser: The browser dynamically renders the notes


sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks Save
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa with note data
    activate server
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: JavaScript updates the notes list dynamically
