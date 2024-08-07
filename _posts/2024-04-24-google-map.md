---
title: "How I integrate Google map with next"
date: 2024-04-24
---
<head>
    <link rel="stylesheet" href="{{site.baseurl}}/assets/2024-04-24/main.css">
</head>
<div class="header text-center">
    <h1>Google Map with Nextjs</h1>
    <div class="col-md-12 header-banner">
        <img src="{{site.baseurl}}/assets/2024-04-24/header-banner.jpg" title="Google Map with Nextjs" width="100%">
    </div>
</div>
<div class="container">
<div class="row">
    <div class="col-sm-12">
        <div class="row">
            <div class="col-sm-12">
                <p>
                    <p>
                        Integrating <a href="https://mapsplatform.google.com/">Google Maps</a> into a Next.js project can enhance your application's interactivity and user experience. In this article, we'll explore how to seamlessly incorporate Google Maps, add markers, 
                        and customize its features using the <code>@vis.gl/react-google-maps version 1.1.0 </code> package
                    </p>
                    <p>The Google Maps API key and Google Map ID used for advanced map features can be obtained from the <a href="https://mapsplatform.google.com/">Google Maps Platform</a>.</p>
                    <a
                    href="https://github.com/sankalpaa/GoogleMapNextjs">Complete source</a>                            
                </p>
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6 leaf right">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Step 1 with Basic marker</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>
                    One of the fundamental tasks when working with maps is displaying a marker. In this article,
                    we'll start with that basic step and explore how to add more and more features to Google
                    Maps. 
                </p>
                <pre>
&lt;APIProvider apiKey={googleMapsApiKey}&gt;
&lt;Map
    defaultCenter={mapCenter}
    defaultZoom={5}
    mapId={googleMapId}
&gt;
    &lt;AdvancedMarker
    position={{ lat: 7.9558296, lng: 80.7572161 }}
    &gt;
    &lt;/AdvancedMarker&gt;
&lt;/Map&gt;
&lt;/APIProvider&gt;
                </pre>
                <a
                    href="https://github.com/sankalpaa/GoogleMapNextjs/tree/e0a997394589ae4662d064bddff28737d62d2efa">See
                    the source</a>
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-md-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-basic-marker.PNG" />
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-multiple-markers.PNG" />
            </div>
        </div>
    </div>
    <div class="col-sm-6 leaf left">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Customizations & Multiple markers</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Here are some customizations to the pin, And adding more markers from an array.
                </p>
                <pre>
places.map((place: Place, key: number) =&gt; (
&lt;AdvancedMarker
    position={{ lat: place.geoPoint.latitude, lng: place.geoPoint.longitude }}
    key={key}
&gt;
    &lt;Pin background={'#FF00FF'} borderColor={'#FF00FF'} glyphColor={'#FFFFFF'}&gt;&lt;/Pin&gt;
&lt;/AdvancedMarker&gt;
))     
                </pre>
                <a
                    href="https://github.com/sankalpaa/GoogleMapNextjs/tree/fcb7d7308cd707c38d22e76e93ffd65432eaba43">See
                    the source</a>
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6 leaf right">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Info window</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Let's first show a small information window, and in the next step, improve it to open only
                    when clicking on the marker.
                </p>
                <pre>
places.map((place: Place, key: number) =&gt; (
&lt;div&gt;
    &lt;AdvancedMarker
    position={{ lat: place.geoPoint.latitude, lng: place.geoPoint.longitude }}
    key={key}
    &gt;
    &lt;Pin background={'#FF00FF'} borderColor={'#FF00FF'} glyphColor={'#FFFFFF'}&gt;&lt;/Pin&gt;
    &lt;/AdvancedMarker&gt;
    &lt;InfoWindow
    position={{ lat: place.geoPoint.latitude, lng: place.geoPoint.longitude }}
    key={key}
    &gt;
    &lt;div&gt;
        &lt;h4&gt;{place.name}&lt;/h4&gt;
        &lt;p&gt;{place.intro}&lt;/p&gt;
    &lt;/div&gt;
    &lt;/InfoWindow&gt;
&lt;/div&gt;
))
                </pre>
                <p><a
                        href="https://github.com/sankalpaa/GoogleMapNextjs/tree/99ea2acf2d6fae7741505527d4d8fdb58dbcd8de">See
                        the source</a></p>
                <p><a
                        href="https://github.com/sankalpaa/GoogleMapNextjs/tree/1d38a2135dc17753980f61d5fd69c6fa219e342c">Next
                        step, Marker click behavior</a></p>
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-marker-info-window.PNG" />
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-Cluster.PNG" />
            </div>
        </div>
    </div>
    <div class="col-sm-6 leaf left">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Marker Clustering</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Clustering is a beautiful feature available in Google Maps; let's see how we can implement
                    it. By using <code>@googlemaps/markerclusterer</code> package.
                </p>
                <pre>
const clusterer = useRef<MarkerClusterer | null>(null);

useEffect(() => {
    if (!map) return;
    if (!clusterer.current) {
        clusterer.current = new MarkerClusterer({ map });
    }
}, [map])

useEffect(() => {
    clusterer.current?.clearMarkers();
    clusterer.current?.addMarkers(Object.values(markers))
}, [markers])

const setMarkerRef = (marker: Marker | null, key: number) => {
    if (marker && markers[key]) return;
    if (!marker && !markers[key]) return;

    setMarkers((prev) => {
        if (marker) {
            return { ...prev, [key]: marker };
        } else {
            const newMarker = { ...prev };
            delete newMarker[key];
            return newMarker;
        }
    });
}
                </pre>
                <p><a
                        href="https://github.com/sankalpaa/GoogleMapNextjs/tree/9eb57a9f3bd7a314e410af6d048b08b0ba3a1805">See
                        the source</a></p>
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6  leaf right">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Beauty of clustering</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>See the beauty of clustering.
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" style="max-height: 300px;" src="{{site.baseurl}}/assets/2024-04-24/google-map-Cluster-markers.PNG" />
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-autocomplete-address.PNG" />
            </div>
        </div>
    </div>
    <div class="col-sm-6 leaf left">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Address search</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Let's integrate Google address search into the map using the <code>@react-google-maps/api</code> npm package.
                </p>
                <pre>
const AutoCompleteOptions = {
componentRestrictions: { country: 'LK' },
};

const onLoad = (autocomplete: google.maps.places.Autocomplete) => {
setSearchResult(autocomplete);
}
                </pre>
                <pre>
&lt;Autocomplete
onLoad={onLoad}
onPlaceChanged={onPlaceChangedEvent}
options={AutoCompleteOptions}
&gt;
&lt;input
className="form-control"
type="text"
placeholder="Enter postcode, suburb or locator name"
&gt;&lt;/input&gt;
&lt;/Autocomplete&gt;
                </pre>
                <p><a href="https://github.com/sankalpaa/GoogleMapNextjs/tree/788c2f2bcef065fb5daf9a3c4526d761cdc71d5b">See the source</a></p>
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6  leaf right">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Locate to the address</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>When the user searches for an address, let's display that location on the map.
                </p>
                <pre>
const zoomToLocation = (location: LatLngLiteral) => {
if (map) {
    map.setCenter({
        lat: location.lat,
        lng: location.lng,
    })
    map.setZoom(10);
}
}

const onPlaceChangedEvent = () => {
if (searchResult) {
    const place = searchResult.getPlace();
    if (place?.geometry?.location) {
        const placeLat = place.geometry?.location?.lat()
        const placeLng = place.geometry?.location?.lng()
        zoomToLocation({
            lat: placeLat,
            lng: placeLng,
        });
    }
}
}
                </pre>
                <a href="https://github.com/sankalpaa/GoogleMapNextjs/commit/2498017ae92416ebb214951b2fc47d95197f892a">See the source</a>
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-center-zoom-location.PNG" />
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-read-user-location.PNG" />
            </div>
        </div>
    </div>
    <div class="col-sm-6 leaf left">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Position of a user</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Use the HTML Geolocation API to get the user's geographical position and display it on the map
                </p>
                <pre>
if (navigator.geolocation) {
navigator.geolocation.getCurrentPosition((position) => {
    zoomToLocation({
        lat: position.coords.latitude,
        lng: position.coords.longitude,
    });
})
}
                </pre>
                <a href="https://github.com/sankalpaa/GoogleMapNextjs/commit/2498017ae92416ebb214951b2fc47d95197f892a">See the source</a>
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-6  leaf right">
        <div class="row">
            <div class="col-sm-12">
                <h3 class="leaf-head">Mark an area</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <p>Here's how to mark an area on Google Maps.
                </p>
                <pre>
new google.maps.Circle({
strokeColor: "#FF0000",
strokeWeight: 2,
fillColor: "#FF0000",
map,
center: latlng,
radius: 3000,
})
                </pre>
                <a href="https://github.com/sankalpaa/GoogleMapNextjs/tree/0890b1fa2ffb4f7a7a6880dc89e5bddee5ecb015">See the source</a>
            </div>
        </div>
    </div>
    <div class="col-sm-6">
        <div class="row image-row">
            <div class="col-sm-12 image-div">
                <img class="img" src="{{site.baseurl}}/assets/2024-04-24/google-map-mark-area-with-circle.PNG" />
            </div>
        </div>
    </div>
</div>
<div class="row center">
    <div class="col-sm-12">
        <div class="row">
            <div class="col-sm-6">
                <div class="row">
                    &nbsp;
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-sm-12">
                <div class="col-md-12 center">
                    <iframe width="560" height="315"
                        src="https://www.youtube.com/embed/N5lGfiGzvV0?si=NXWeqavcBiZhdl2u"
                        title="YouTube video player" frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                        referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
            </div>
        </div>
    </div>
</div>
</div>
