---
layout: page
title: Trondheim
---

<script src='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.js'></script>
<link href='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.css' rel='stylesheet' />
<style>
  #map { 
    position: top:0; bottom:0; height: 400px; max-width: 100%; 
  }
  .marker {
    background-image: url('../assets/img/poi.png');
    background-size: cover;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
  }
  .mapboxgl-popup {
    max-width: 200px;
  }

  .mapboxgl-popup-content {
    text-align: center;
    font-family: 'Open Sans', sans-serif;
  }
</style>
  
- [Registration](#registration)
- [Support](#support)
- [Venues](#venues)
- [Travel](#travel)

<h3 id="registation">Registration</h3>  
The registration for ICLI will open late December. 
Early bird registration will close on January 9th, but it is possible to register up until the conference starts.
The conference fee is reduced for participants without an institutional affiliation, to support participation for independent artists and researchers. Bachelor and master students may  use the reduced fee too.
Early bird registration (before January 9th) also get a reduced conference fee.

##### Prices
Full conference fee: 330 EUR, with an early bird price of 250 EUR  
The reduced fee for independent artists and students: 170 EUR, with an early bird fee of 130 EUR.

The conference fee includes access to all the events, coffee and lunch for all three days, a copy of the Meta.Morf catalogue, and inclusion of your submission in the proceedings.

<h3 id="support">Support</h3>

We are in dialogue with the Norwegian embassies in countries that has participants to ICLI. It might be possible to get travel support for participants. Participants can contact the Norwegian embassy in their home country to inquire further for this possibility.  
Another option is also the [EEA Open Call](https://www.eeagrants.gov.pt/en/programmes/bilateral-relations/calls/fbr-open-call-1/) for bilateral relations: 

Activities that can be supported by the FBR Open Call #1 could be, as examples: matchmaking events; technical cooperation and exchange of experts; short-term internships; training actions; workshops and seminars on topics of common interest.
The deadline for selecting the third phase of applications ends on 10.01.2020, GMT 12:00:00.
We have been informed that participants from eligible countries could apply here.

<h3 id="venues">Venues</h3>  



<div id='map'></div>

<script>
  mapboxgl.accessToken = 'pk.eyJ1IjoibGl2ZWludGVyZmFjZXMiLCJhIjoiY2swcDZ5Mno3MGYxdjNnbjZmYmJsdHJkaSJ9.bfcq3YulwNY3JekbxvASOQ';
   
  var map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/streets-v9',
    center: [10.406494, 63.434764],
    zoom: 12
  });
   
  var geojson = {
    type: 'FeatureCollection',
    features: [{
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.401446, 63.438835]
      },
      properties: {
        title: 'Rockheim',
        description: 'Brattørkaia 14, 7010 Trondheim'
      }
    },
    {
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.411141, 63.434183]
      },
      properties: {
        title: 'Dokkhuset',
        description: 'Dokkparken 4, 7042 Trondheim'
      }
    },
    {
      type: 'Feature',
      geometry: {
        type: 'Point',
        coordinates: [10.395398, 63.426880]
      },
      properties: {
        title: 'Nidarosdomen',
        description: 'Kongsgårdsgata 2, 7013 Trondheim'
      }
    }]
  };
   
  map.on('load', function () {
    geojson.features.forEach(function(marker) {
      // create a HTML element for each feature
      var el = document.createElement('div');
      el.className = 'marker';

      // make a marker for each feature and add to the map
      new mapboxgl.Marker(el)
      .setLngLat(marker.geometry.coordinates)
      // add popups
      .setPopup(new mapboxgl.Popup({ offset: 25, maxWidth: 150, anchor: 'left' })
        .setHTML(
          '<h5>' + marker.properties.title + '</h5>' + 
          '<p>' + marker.properties.description + '</p>' + 
          // use the (...)_thumb.jpg images
          '<img src=\'../assets/img/' + marker.properties.title.toLowerCase() + '_thumb.jpg\'></img>'
        ))
      .addTo(map);
    });
  });
 
</script>
[Rockheim](https://rockheim.no/) is the National Museum of Popular Music that collects, preserve and disseminates
Norwegian popular music from the 1950s until today. Rockheim is located on the Brattørkaia in Trondheim.  

[Dokkhuset](http://dokkhuset.no/) is a concert venue at Nedre Elvehavn in Trondheim. The Dokkhuset scene presents chamber music and jazz, new music, world music and other forms of musical expression.

[Nidaros Cathedral](https://www.nidarosdomen.no/en/) is the world’s northernmost medieval cathedral and Norway’s national sanctuary.

<h3 id="travel">Travel to Trondheim</h3>  

Værnes Airport Trondheim has national and international flight connections.
There are two companies offering direct bus services into Trondheim City, departing every 15min.  

* [Værnes Ekspressen](https://vaernesekspressen.no/)
* [Flybussen](https://www.flybussen.no/?dir=to)

The train travels along the coast line to Trondheim Sentrum and offers a beautiful landscape, it
runs once every hour. 

You can also travel to Trondheim by train from Oslo. The train from Oslo to to Trondheim also pass Gardermoen airport.
Web site for train timetables and tickets: [vy.no](https://www.vy.no/en)
