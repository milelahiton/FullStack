sequenceDiagram
    participant browser
    participant server

    Note over browser: El usuario escribe la nota y pulsa "Save"
    Note right of browser: El JS añade la nota a la lista localmente y la dibuja en pantalla

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: Se envía el JSON: { "content": "nueva nota", "date": "2026-..." }
    server-->>browser: HTTP 201 Created (JSON confirmación)
    deactivate server

    Note right of browser: No hay más peticiones, la página permanece igual