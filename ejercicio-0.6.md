sequenceDiagram
    participant browser
    participant server

    Note right of browser: Usuario escribe una nota y presiona "Save"

    browser->>server: POST /new_note_spa
    activate server
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: JS agrega la nueva nota al estado en memoria

    Note right of browser: La vista se actualiza dinámicamente sin recargar la página
