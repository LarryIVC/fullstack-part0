```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    browser->>server: GET https://fonts.googleapis.com/css?family=Lato:300,400,700,900
    activate server
    server-->>browser: the font file from Google Fonts
    deactivate server

    browser->>server: GET https://fonts.gstatic.com/s/lato/v24/S6uyw4BMUTPHjx4wXg.woff2
    activate server
    server-->>browser: the font file from Google Fonts
    deactivate server

    Note right of browser: The browser renders the notes and the font    

```

