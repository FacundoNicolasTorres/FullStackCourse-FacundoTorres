## Activitie 0.5 Diagrama de aplicación de una sola página

### Crea un diagrama que describa la situación en la que el usuario accede a la versión de aplicación de una sola página de la aplicación de notas en https://studies.cs.helsinki.fi/exampleapp/spa.

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa;
    activate server;
    server-->>browser: HTML document spa.html;
    deactivate server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    activate server;
    server-->>browser: the css file main.css;
    deactivate server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js;
    activate server;
    server-->>browser: the JavaScript file spa.js;
    deactivate server;

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json;
    activate server;
    server-->>browser: [{ "content": "I Love Empanadas", "date": "2025-05-27" }, ... ];
    deactivate server;

    Note right of browser: The browser executes the callback function that renders the notes;
```

