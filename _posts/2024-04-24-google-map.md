---
title: "How I integrate Google map with next"
date: 2024-04-24
---
1. Basic map
there are few ways we can integrate google map
we going to follow API provider for this implementation.
Error
![image](https://github.com/sankalpaa/ConceptWelder/assets/7065759/c81b2ee3-c6c9-4e0d-b27b-890ccfd16348)
Solution
`'use client';`

Error
![image](https://github.com/sankalpaa/ConceptWelder/assets/7065759/3c5b6565-a63d-4dcc-820a-cd900b7b88e1)
Solution
Get google map API key from google cloud platform.

basic map
`    <div style={{ height: "100vh", width: "100%" }}>
      <APIProvider apiKey={googleMapsApiKey}>
        <Map center={mapCenter} zoom={9}></Map>
      </APIProvider>
    </div>`
importent points 
 set google map api key
 set style to set width and height

3. Show basic marker
4. Show more markers
5. Show info window
6. Show cluster
7. Show address search
8. Get your location (Browser)
9. Show address
   
