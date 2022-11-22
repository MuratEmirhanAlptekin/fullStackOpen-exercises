sequenceDiagram

browser->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
note right of server: he server responds with HTTP status code 302. This is a URL redirect, with which the server asks the browser to do a new HTTP GET request to the address defined in the header's Location - the address notes.
server->browser: redirect to https://studies.cs.helsinki.fi/exampleapp/notes
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
server->browser: HTML
browser->server: https://studies.cs.helsinki.fi/exampleapp/main.css
server->browser: main.css
browser->server: https://studies.cs.helsinki.fi/exampleapp/main.js
server->browser: main.js
note left of browser: main.js gets interpreted and it requests data.json
browser->server: https://studies.cs.helsinki.fi/exampleapp/data.json
server->browser: data.json
