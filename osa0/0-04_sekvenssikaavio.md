sequenceDiagram
  participant browser
  participant server

  %% Käyttäjä lähettää lomakkeen
  browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
  activate server
  server ->> browser: Ei vastausdataa koska pyyntö uudelleenohjattu
  deactivate server

  %% Selaimen uudelleenohjaus
  browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server ->> browser: HTML document
  deactivate server
  
  %% Haetaan staattiset osat
  browser ->> server: GET /exampleapp/main.css
  activate server
  server ->> browser: CSS styling
  deactivate server
  
  %% Lisätään uusi note listaan ja haetaan data.json sivulle
  browser ->> server: GET /exampleapp/main.js
  activate server
  server ->> browser: JS file
  deactivate server

  %% Kaikki notet
  browser ->> server: GET /exampleapp/data.json
  activate server
  server ->> browser: JSON
  deactivate server
