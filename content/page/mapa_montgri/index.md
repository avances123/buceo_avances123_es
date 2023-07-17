---
title: "Cuevas del Montgri"
license: false
date: 2023-07-13
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
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.css" integrity="sha512-Zcn6bjR/8RZbLEpLIeOwNtzREBAJnUKESxces60Mpoj+2okopSAcSUIUOseddDm0cxnGQzxIR7vJgsLZbdLE3w==" crossorigin="anonymous" referrerpolicy="no-referrer" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.js" integrity="sha512-BwHfrr4c9kmRkLw6iXFdzcdWV/PGkVgiIyIWLLlTSXzWQzxuSg4DiQUCpauz/EWjgk5TYQqX/kvn9pG1NpYfqg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet-ajax/2.1.0/leaflet.ajax.min.js" integrity="sha512-Abr21JO2YqcJ03XGZRPuZSWKBhJpUAR6+2wH5zBeO4wAw4oksr8PRdF+BKIRsxvCdq+Mv4670rZ+dLnIyabbGw==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
</head>
<body>
<div id="map" style="width: 100%; height: 600px"></div>

<script>
  var
    tileUrl,
    map = L.map('map').setView([42.111202,3.170544], 16);

  var OpenStreetMap_Mapnik = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
	maxZoom: 19,
	attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  });

  var Esri_WorldImagery = L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
	attribution: ''
  });

  Esri_WorldImagery.addTo(map);

  var geojsonLayer = new L.GeoJSON.AJAX("https://buceo.avances123.es/leaflet_montgri/cuevas_montgri.geojson",{
    onEachFeature: function (feature, layer) {
        layer.bindPopup(
        '<h1>'+feature.properties.nombre+'</h1>'+
        '<h5>Desarrollo: '+feature.properties.desarrollo+'m</h5>'+
        '<a href="' + feature.properties.url + '"><img src="' + feature.properties.topografia +'" alt="HTML tutorial" style="width:200px;height:100px;"></a>'
        );
    }
  });       

  geojsonLayer
  .addTo(map);



  
</script>
</body>
</html>