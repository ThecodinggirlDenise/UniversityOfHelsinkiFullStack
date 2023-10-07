 ```mermaid
 sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Access https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: Request for SPA(Single Page Application) page
    Server-->>Browser: HTML for SPA(Single Page Application) page
    Browser->>Server: Fetches spa.js
    Server-->>Browser: spa.js
    Browser->>User: Renders the SPA page

    User->>Browser: Create new notes
    Browser->>User: Manipulates the DOM to add the notes
    Browser->>Server: Send POST request to /new_notes_spa
    Browser--x User: Notes added to the page
    Browser->>Server: POST request data (JSON)

    Server->>Server: Process and save the new note
    Server-->>Browser: Response with status code 201 (Created)
    Browser->>User: Display notes without page reload

    Note right of Browser: SPA-style interaction\nwith server using AJAX

