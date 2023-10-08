```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser:User should enter text for a new note
    User->>Browser: Then she/he should click "Save" button

    Browser->>Browser: Validate and process user input
    Browser->>Server: Send POST request to /new_note_spa
    Browser--x User: Clear input field
    Browser--x User: Display a loading indicator

    Server->>Server: Process and save the new note
    Server-->>Browser: Respond with status code 201 (Created)

    Browser->>Browser: Removes loading indicator
    Browser->>Browser: Adds the new note to the list
    Browser->>User: Displays the new note on the page

    Note right of Browser: SPA-style interaction\nwith server using AJAX


