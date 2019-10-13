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
  
[Venues](#venues)
[Travel](#travel)
[Contact](#contact)

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

<h3 id="venues">Venues</h3>  

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
goes one time per hour. 

You can also travel to Trondheim by train from Oslo. The train from Oslo to to Trondheim also pass Gardermoen airport.
Web site for train timetables and tickets: [vy.no](https://www.vy.no/en)

<h3 id="contact">Contact</h3>
Email inquiries: [liveinterfaces (at) gmail.com](mailto:liveinterfaces@gmail.com)
