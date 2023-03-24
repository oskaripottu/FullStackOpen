sequenceDiagram
  participant browser
  participant server

  browser ->>server: GET https://studies.cs.helsinki.fi/exampleapp/new_note
  activate server
  server-->browser: Ei vastausdataa koska pyyntö uudelleenohjattu
  deactivate server
  
  browser->>server: https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server-->browser: HTML document
  deactivate server
  
  browser->>server: https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server-->browser: CSS styling
  deactivate server
  
  browser->>server: https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server-->browser: JS code
  deactivate server
