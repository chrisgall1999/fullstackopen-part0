sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    server-->>browser: HTML SPA
    deactivate server

    browser->>server: GET /main.css
    server-->>browser: CSS

    browser->>server: GET /spa.js
    server-->>browser: JavaScript SPA

    Note right of browser: JS se ejecuta y hace GET al JSON de notas

    browser->>server: GET /data.json
    server-->>browser: JSON de notas

    Note right of browser: JS renderiza las notas en la vista, sin recargar la página
