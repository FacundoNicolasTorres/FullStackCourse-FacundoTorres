## Activitie 0.6 Nueva nota en diagrama de aplicación de una sola página

### Crea un diagrama que represente la situación en la que el usuario crea una nueva nota utilizando la versión de una sola página de la aplicación.

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    Note right of browser: User writes a new note and submits the form;

    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa;
    activate server;
    server-->>browser: HTTP Status Code 201;
    deactivate server;

    Note right of browser: No page reload;
```