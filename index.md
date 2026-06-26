<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css"/>
</head>
<body>
  <div id="map" style="height: 100vh"></div>
  <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
  <script>
    var map = L.map('map').setView([-6.067, -49.903], 10); // Parauapebas
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);
    
    // Carrega seu GeoJSON da pasta /data
    fetch('data/limite_pa.geojson')
      .then(res => res.json())
      .then(data => L.geoJSON(data).addTo(map));
  </script>
</body>
</html>