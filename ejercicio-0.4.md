

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: Usuario escribe una nota y presiona el botón "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: 302 Redirect a /notes
    deactivate server

    browser->>server: GET /notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /main.css
    server-->>browser: CSS

    browser->>server: GET /main.js
    server-->>browser: JavaScript

    Note right of browser: El navegador ejecuta el JS que hace GET a los datos JSON

    browser->>server: GET /data.json
    server-->>browser: JSON actualizado (incluye la nueva nota)

    Note right of browser: El navegador renderiza las notas en pantalla

