title Muistiinpanon luominen

selain->palvelin: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_not

note over palvelin:
Palvelin luo uutta muistiinpanoa 
vastaavan olion ja laittaa sen 
muistiinpanot sisältävään taulukkoon
end note

palvelin-->selain: redirect to Location Notes
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
palvelin-->selain: HTML-koodi
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
palvelin-->selain: main.css
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
palvelin-->selain: main.js

note over selain:
selain alkaa suorittaa js-koodia
joka pyytää JSON-datan palvelimelta
end note

selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
palvelin-->selain: JSON data

note over selain:
selain suorittaa tapahtumankäsittelijän
joka renderöi muistiinpanot näytölle
end note