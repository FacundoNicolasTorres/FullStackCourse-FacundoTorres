## Activitie0.4
### Crea un diagrama similar que describa la situación en la que el usuario crea una nueva nota en la página https://studies.cs.helsinki.fi/exampleapp/notes escribiendo algo en el campo de texto y haciendo clic en el botón Save.

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note;
    activate server;
    server-->>browser: HTTP Status Code 302;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes;
    activate server;
    server-->>browser: HTML document;
    deactivate server;

     browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    activate server;
    server-->>browser: the css file main.css;
    deactivate server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js;
    activate server;
    server-->>browser: the JavaScript file main.js;
    deactivate server;

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server;

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json;
    activate server;
    server-->>browser: [{ "content": "I Love Empanadas", "date": "2025-05-27" }, ... ];
    deactivate server;

    Note right of browser: The browser executes the callback function that renders the notes
```