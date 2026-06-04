## Exercise 0.6 — New note (SPA)

```mermaid
sequenceDiagram
    participant browser
    participant server

    note over browser: User types note, clicks Save
    note over browser: JS intercepts submit (e.preventDefault)
    note over browser: JS adds note to page immediately

    browser->>server: POST /new_note_spa (JSON body)
    activate server
    server-->>browser: 201 Created
    deactivate server

    note over browser: No reload, no extra requests
```