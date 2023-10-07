```mermaid

sequenceDiagram
    participant browser
    participant server
    participant database

    Note right of browser: User writes a new note(Hi for example) and clicks Save

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server->>database: Insert new note into the database
    activate database
    database-->>server: Confirmation (e.g., "Note saved successfully")
    deactivate database
    server-->>browser: Confirmation
    deactivate server

    Note right of browser: Browser updates the UI to display the new note(Hi for example)
    
