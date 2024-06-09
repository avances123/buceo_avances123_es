---
title: "Cuevas del Montgri"
license: false
date: 2024-05-06
slug: "mapa_montgri"
description: Mapa con las cuevas en el montgri
menu:
    main:
        weight: 2
        params: 
            icon: archives
---


<!DOCTYPE html>
<html>
<head>
  <title>Static Data with Leaflet</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/gh/ptma/Leaflet.Legend@master/src/leaflet.legend.css" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.css" integrity="sha512-Zcn6bjR/8RZbLEpLIeOwNtzREBAJnUKESxces60Mpoj+2okopSAcSUIUOseddDm0cxnGQzxIR7vJgsLZbdLE3w==" crossorigin="anonymous" referrerpolicy="no-referrer" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.js" integrity="sha512-BwHfrr4c9kmRkLw6iXFdzcdWV/PGkVgiIyIWLLlTSXzWQzxuSg4DiQUCpauz/EWjgk5TYQqX/kvn9pG1NpYfqg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet-ajax/2.1.0/leaflet.ajax.min.js" integrity="sha512-Abr21JO2YqcJ03XGZRPuZSWKBhJpUAR6+2wH5zBeO4wAw4oksr8PRdF+BKIRsxvCdq+Mv4670rZ+dLnIyabbGw==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  <script src="https://cdn.jsdelivr.net/gh/ptma/Leaflet.Legend@master/src/leaflet.legend.js"></script>
</head>
<body>
<div id="map" style="width: 100%; height: 600px"></div>

<style>

.leaflet-legend{
  color: #000;
  font-size: 12px;
}
</style>


<script>
  var tileUrl;
  var bounds = new L.LatLngBounds(new L.LatLng(42.0042, 3.13024), new L.LatLng(42.21774, 3.28647));

  var map = L.map('map', {
    center: bounds.getCenter(),
    minZoom: 16,
    maxZoom: 18,
    maxBounds: bounds,
    maxBoundsViscosity: 0.75
  }).setView([42.111202,3.170544], 16);

  var OpenStreetMap_Mapnik = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
	maxZoom: 19,
	attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  });

  var Esri_WorldImagery = L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
	attribution: ''
  });

  Esri_WorldImagery.addTo(map);

  var estilo_cuevas = {
      radius: 6,
      fillColor: "#ff0000",
      color: "#000",
      weight: 1,
      opacity: 1,
      fillOpacity: 0.8
  };

  var estilo_tuneles = {
      radius: 6,
      fillColor: "#00ff00",
      color: "#000",
      weight: 1,
      opacity: 1,
      fillOpacity: 0.8
  };

  var estilo_accesos = {
      radius: 6,
      fillColor: "#0000ff",
      color: "#000",
      weight: 1,
      opacity: 1,
      fillOpacity: 0.8
  };


  var geojsonLayer = new L.GeoJSON.AJAX("https://buceo.avances123.es/leaflet_montgri/cuevas_montgri.geojson",{
    onEachFeature: function (feature, layer) {
        if (feature.properties.url){
          layer.bindPopup(
            '<h1>'+feature.properties.nombre+'</h1>'+
            '<h5>Desarrollo: '+feature.properties.desarrollo+'m</h5>'+
            '<a href="' + feature.properties.url + '"><img src="' + feature.properties.topografia +'" alt="'+ feature.properties.nombre +'" style="width:200px;height:100px;"></a>'
          );
        } else {
          layer.bindPopup(
            '<h1>'+feature.properties.nombre+'</h1>'+
          );
        }

    },
    pointToLayer: function (feature, latlng) {
        var tipo = feature.properties.tipo;
        var estilo = estilo_cuevas;
        if (tipo == 'cueva'){
          estilo = estilo_cuevas;
        }
        if (tipo == 'tunel'){
          estilo = estilo_tuneles;
        }
        if (tipo == 'acceso'){
          estilo = estilo_accesos;
        }

        return L.circleMarker(latlng, estilo);
    }
  });       

  geojsonLayer
  .addTo(map);




var marker1 = L.circleMarker([0.0], estilo_accesos)


var Legend =  new L.Control.Legend({
    position: "bottomleft",
    collapsed: false,
    symbolWidth: 24,
    opacity: 1,
    column: 1,
    title: "Tipos de marcador",
    legends: [{
                label: "Acceso",
                type: "circle",
                radius: 6,
                fillColor: "#0000ff",
                color: "#000",
                weight: 1,
                opacity: 1,
                fillOpacity: 1,
                inactive: false,
            },
            {
                label: "Túnel",
                type: "circle",
                radius: 6,
                fillColor: "#00ff00",
                color: "#000",
                weight: 1,
                opacity: 1,
                fillOpacity: 1,
                inactive: false,
            },
            {
                label: "Cueva",
                type: "circle",
                radius: 6,
                fillColor: "#ff0000",
                color: "#000",
                weight: 1,
                opacity: 1,
                fillOpacity: 1,
                inactive: false,
            }]
});
map.addControl( Legend );


</script>
</body>
</html>


Desde hace tiempo estoy escaneando la pared de la peninsula del montgo, si tengo oportunidad, topografío cada cueva que veo medianamente significativa. Para ello empleo mi scooter para viajar al punto, mi ordenador de buceo y la boya para ascender a la superficie y tomar las coordenadas de la entrada, y una plantilla, hilo y cookies para la poligonal. Ademas grabo desde mi casco y otra pasada manual con la gopro para luego en casa dibujar las paredes de la cueva.

Espero poder ayudar a los siguiente buceadores a conocer mas esta fantastica pared y que puedan disponer de la mayor informacion posible.