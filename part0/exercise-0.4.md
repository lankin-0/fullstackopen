## Exercise 0.4 — New note (traditional app)

```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST /new_note (form data)
    activate server
    server-->>browser: 302 Redirect to /notes
    deactivate server

    browser->>server: GET /notes
    activate server
    server-->>browser: HTML
    deactivate server

    browser->>server: GET /main.css
    activate server
    server-->>browser: CSS
    deactivate server

    browser->>server: GET /main.js
    activate server
    server-->>browser: JavaScript
    deactivate server

    browser->>server: GET /data.json
    activate server
    server-->>browser: JSON (includes new note)
    deactivate server

    note over browser: JS runs, builds DOM, note appears
```