---
layout: page
title: About
permalink: /about/
---

# Background

## My name is Aidan

<head>
<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
<style>
    #map-taiwan, #map-hongkong {
        height: 400px;
        width: 100%;
    }
</style>
</head>


<h3>Taiwan Map</h3>
<div id="map-taiwan"></div>

<h3>Hong Kong Map</h3>
<div id="map-hongkong"></div>

<div>
<h3>I'm a 2nd gen Asian-American</h3>
<h3>My mom is from Taiwan and my dad is from Hong Kong</h3>
<h3>I used to travel to Taiwan and Hong Kong every summer as a kid to visit my family, eat yummy food, and visit historic spots.</h3>
</div>

<div><h3 id="factDisplay">Click the button to see a fun fact!</h3></div>
<button id="generateBtn">Generate Fun Fact</button>

<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
<script>
    // Initialize the Taiwan map
    const mapTaiwan = L.map('map-taiwan').setView([23.6978, 120.9605], 7);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; OpenStreetMap contributors'
    }).addTo(mapTaiwan);

    // Initialize the Hong Kong map
    const mapHongKong = L.map('map-hongkong').setView([22.3193, 114.1694], 10);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; OpenStreetMap contributors'
    }).addTo(mapHongKong);

    // Function to fetch place details from Google Places API
    function fetchPlaceDetails(placeId, marker) {
        fetch(`https://maps.googleapis.com/maps/api/place/details/json?placeid=${placeId}&key=AIzaSyDFVflW94dxDByHVvyZbcArrlkKXac8ZTs`)
            .then(response => response.json())
            .then(data => {
                const details = data.result;
                const result = {
                    name: details.name,
                    address: details.formatted_address,
                    photos: details.photos ? details.photos.map(photo => `https://maps.googleapis.com/maps/api/place/photo?maxwidth=400&photoreference=${photo.photo_reference}&key=AIzaSyDFVflW94dxDByHVvyZbcArrlkKXac8ZTs`) : [],
                    reviews: details.reviews ? details.reviews.map(review => review.text) : []
                };

                let popupContent = `<b>${result.name}</b><br>${result.address}<br>`;
                result.photos.forEach(photo => {
                    popupContent += `<img src="${photo}" alt="photo" width="100px"><br>`;
                });
                popupContent += "<b>Reviews:</b><br>";
                result.reviews.forEach(review => {
                    popupContent += `<p>${review}</p>`;
                });

                marker.bindPopup(popupContent).openPopup();
            })
            .catch(error => {
                console.error('Error fetching place details:', error);
                marker.bindPopup("Details not available").openPopup();
            });
    }

    // Add markers for Taiwan
    const taipei101Marker = L.marker([25.0330, 121.5654]).addTo(mapTaiwan)
        .bindPopup("Loading...")
        .on('click', function () {
            fetchPlaceDetails('ChIJN1t_tDeuEmsRUsoyG83frY4', taipei101Marker); 
        });

    // Add markers for Hong Kong
    const victoriaPeakMarker = L.marker([22.3964, 114.1095]).addTo(mapHongKong)
        .bindPopup("Loading...")
        .on('click', function () {
            fetchPlaceDetails('ChIJyWEp3q0LkFQR9hZ4T_g4Frw', victoriaPeakMarker); 
        });
</script>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const facts = [
        "I can solve a Rubiks cube. My fastest time was 6 seconds",
        "My favorite subject is math",
        "I'm going to 2 concerts in September: Rocco and wave to earth",
        "I can build keyboards.",
    ];

    const factDisplay = document.getElementById('factDisplay');
    const generateBtn = document.getElementById('generateBtn');

    generateBtn.addEventListener('click', function() {
        const randomIndex = Math.floor(Math.random() * facts.length);
        factDisplay.innerHTML = facts[randomIndex];
    });
});
</script>
