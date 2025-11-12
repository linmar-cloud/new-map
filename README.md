# new-map
mapppppp
<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Global Flag Map</title>
    <style>
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
      #map {
        height: 100%;
        width: 100%;
      }
    </style>
  </head>
  <body>
    <div id="map"></div>

    <script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap" async defer></script>
    <script>
      function initMap() {
        const map = new google.maps.Map(document.getElementById("map"), {
          center: { lat: 32.88506, lng: 12.144791 },
          zoom: 2,
        });

        const locations = [
          { lat: -13.531925, lng: -71.966805, title: "Cusco, Peru" },
          { lat: 35.829537, lng: 128.563954, title: "Daegu, South Korea" },
          { lat: 33.51336, lng: 36.27715, title: "Damascus, Syria" },
          { lat: 12.962955, lng: 77.578567, title: "Bengaluru, India" },
          { lat: -36.851724, lng: 174.764905, title: "Auckland, New Zealand" },
          { lat: 50.064536, lng: 19.943203, title: "Krakow, Poland" },
          { lat: 14.596322, lng: 120.983146, title: "Manila, Philippines" },
          { lat: -1.292152, lng: 36.819216, title: "Nairobi, Kenya" },
          { lat: 46.063608, lng: -118.342034, title: "Walla Walla, Washington (US)" },
          { lat: 31.621793, lng: -7.989471, title: "Marrakesh, Morocco" },
        ];

        const iconUrl = "https://developers.google.com/maps/documentation/javascript/examples/full/images/beachflag.png";

        locations.forEach(loc => {
          new google.maps.Marker({
            position: { lat: loc.lat, lng: loc.lng },
            map,
            title: loc.title,
            icon: {
              url: iconUrl,
              scaledSize: new google.maps.Size(32, 32),
            },
          });
        });
      }
    </script>
  </body>
</html>
