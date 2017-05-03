# Spots-Terrass
<!DOCTYPE html>
<html> 
<head> 
  <meta http-equiv="content-type" content="text/html; charset=UTF-8" /> 
  <title> Spots Terrassa </title> 
  <script src="http://maps.google.com/maps/api/js?sensor=false" 
          type="text/javascript"></script>
</head> 
<body>
  <div id="mapa_pr" style="height: 480px; width: 300px"></div>

  <script type="text/javascript">
    var sitios = [
      ['<a href="file:///C:/Users/152S01E02/Downloads/fontvella%20(4).html">Font Vella</a>', 41.5629819,2.0148684, 9],
      ['Torre Del Palau', 41.5624187,2.010783, 8],
      ['La Caixa', 41.5666998,2.0061774, 7],
      ['La Policia', 41.5591452,2.0275142, 6],
      ['Plaça Ricard Camin', 41.5669614,2.0069204, 5],
      ['Carrer Matadepera', 41.578399,2.0176167, 4],
      ['Maurina Xemeneia', 41.5580429,1.9992942, 3],
      ['Las Canteras', 36.5372, -6.1851, 2],
      ['Polideportivo', 36.5268, -6.1936, 1]
    ];

    var map = new google.maps.Map(document.getElementById("mapa_pr"), {
    center: new google.maps.LatLng(41.5667,2.0167),
      zoom: 13,
      mapTypeId: google.maps.MapTypeId.SATELLITE
    });

    var infowindow = new google.maps.InfoWindow();

    var marker, i;

    for (i = 0; i < sitios.length; i++) {  
        marker = new google.maps.Marker({
        position: new google.maps.LatLng(sitios[i][1], sitios[i][2]),
        map: map
      });

      google.maps.event.addListener(marker, 'click', (function(marker, i) {
        return function() {
          infowindow.setContent(sitios[i][0]);
          infowindow.open(map, marker);
        }
      })(marker, i));
    }
  </script>
</body>
</html>
