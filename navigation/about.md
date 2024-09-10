---
layout: page
title: About
permalink: /about/
---



<head>
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <style>
        .map-container {
            display: flex;
            justify-content: space-around;
            align-items: flex-start;
            gap: 20px; /* Space between the maps */
            margin-bottom: 20px;
        }

        #map-taiwan,
        #map-hongkong {
            flex: 1; /* Ensures both maps take equal space */
            height: 400px;
            min-width: 300px; /* Ensures the maps do not become too small */
            margin: 10px;
        }

        @media (max-width: 800px) {
            .map-container {
                flex-direction: column; /* Stacks maps vertically on smaller screens */
                align-items: center;
            }
        }

        body {
            margin: 0px;
            font-family: "Cedarville Cursive", cursive;
        }

        div#background {
            height: 700px;
            width: 100%;
            background-image: url(http://garchitecture.ca/php/images/headers/wood.jpg);
            padding-top: 20px;
        }

        div#gallery {
            width: 800px;
            margin: auto;
        }

        #background img {
            height: 150px;
            margin: 0px;
        }

        #background figure {
            float: left;
            position: relative;
            background-color: white;
            text-align: center;
            font-size: 15px;
            padding: 10px;
            margin: 10px;
            box-shadow: 1px 2px 3px black;
        }

        figure.pic1 {
            -webkit-transform: rotate(-10deg);
            z-index: 1;
        }

        figure.pic2 {
            -webkit-transform: rotate(15deg);
            z-index: 2;
        }

        figure.pic3 {
            -webkit-transform: rotate(-25deg);
            z-index: 1;
        }

        figure.pic4 {
            -webkit-transform: rotate(5deg);
            z-index: 1;
        }

        figure.pic5 {
            -webkit-transform: rotate(5deg);
            z-index: 1;
        }

        figure.pic6 {
            -webkit-transform: rotate(-8deg);
            z-index: 1;
        }

        figure.pic7 {
            -webkit-transform: rotate(2deg);
            z-index: 1;
        }

        figure.pic8 {
            -webkit-transform: rotate(-13deg);
            z-index: 1;
        }

        figure.pic9 {
            -webkit-transform: rotate(-7deg);
            z-index: 1;
        }

        figure.pic10 {
            -webkit-transform: rotate(2deg);
            z-index: 1;
        }

        figure.pic11 {
            -webkit-transform: rotate(-3deg);
            z-index: 1;
        }

        #background figure:hover {
            box-shadow: 5px 10px 100px black;
            -webkit-transform: scale(1.1, 1.1);
            z-index: 20;
        }

        .keyboard-container {
            display: flex;
            justify-content: space-around;
            margin: 20px;
        }

        .keyboard-item {
            text-align: center;
            outline: 5px solid rgb(255, 127, 80); 
            padding: 10px;
        }

        .keyboard-item img {
            width: 300px; 
        }
        #gallery figure {
            display: inline-block;
            margin: 20px;
            text-align: center;
            outline: 5px solid rgb(255, 127, 80); 
            padding: 10px;
        }

        #gallery img {
            width: 300px;
            height: auto;
        }

        #background-info {
            outline: 5px solid rgb(255, 127, 80); 
            padding: 20px;
            margin: 20px;

            
        }
    </style>
</head>

<h1><img src="{{site.baseurl}}/images/about/fumu.png" height="60" alt="">Where My Parents are From</h1>

<h3><img src="{{site.baseurl}}/images/about/taibei.png" height="60" alt="">Maps of Taiwan and Hong Kong</h3>
<div class="map-container">
    <div id="map-taiwan"></div>
    <div id="map-hongkong"></div>
</div>

<div id="background-info">
    <h1 style="color: #FFFFFF">
        <img src="{{site.baseurl}}/images/about/qiyuan.png" height="60" alt="">
        My Background
    </h1>
    <ul>
        <ol><h3>I'm a 2nd gen Asian-American</h3></ol>
        <ol><h3>My mom is from Taiwan and my dad is from Hong Kong</h3></ol>
        <ol><h3>
            I used to travel to Taiwan and Hong Kong every summer as a kid to visit
            my family, eat yummy food, and visit historic spots.
        </h3></ol>
    </ul>
    <div><h3 id="factDisplay">Click the button to see a fun fact!</h3></div>
    <button id="generateBtn" style="color: #FF7F50">Generate Fun Fact</button>
</div>



<link
    href="https://fonts.googleapis.com/css?family=Cedarville+Cursive"
    rel="stylesheet"
    type="text/css"
/>

<h1 style="color: #FFFFFF"><img src="{{site.baseurl}}/images/about/jianpan.png" height="60" alt="">Keyboards I Made</h1>
<div class="keyboard-container">
    <div class="keyboard-item">
        <img
            src="{{site.baseurl}}/images/about/mkeyboard.jpeg"
            alt="Keyboard 1"
        />
        <p><ul>
        <h3>Price: $200</h3>
        <ol>PCB, Foam, PC Plate, Case: KBDfans KBD67 Lite Mechanical Keyboard DIY Kit</ol>
        <ol>Switches: Gateron X Yellows lubed with Krytox 205G0 and Krytox GPL 105 and Deskey Switch Films</ol>
        <ol>Stabilizers: Durock V2 Stabilizers Screw-In lubed with Permatex 22058 Dielectric Grease</ol>
        <ol>Keycaps: EnjoyPBT Miami Nights Keycap Set Doubleshot ABS - Miami Nights </ol>
        </ul></p>
    </div>
    <div class="keyboard-item">
        <img
            src="{{site.baseurl}}/images/about/pkeyboard.jpeg"
            alt="Keyboard 2"
        />
        <p><ul>
        <h3>Price: $300</h3>
        <ol>PCB, Foam, Plate(FR4), Case(Black/Burgundy): QK60</ol>
        <ol>Switches: Gateron Oil King 5 pin lubed with Krytox 205G0 and Krytox GPL 105 with TX Switch Films</ol>
        <ol>Keycaps: Idobao DSA Black Sakura Japanese Keycaps</ol>
        </ul></p>
    </div>
</div>
<h1 style="color: #FFFFFF"><img src="{{site.baseurl}}/images/about/zhaopian.png" height="60" alt="">Recent Pictures</h1>
<div id="background">
    <div id="gallery">
        <figure class="pic1">
            <img src="{{site.baseurl}}/images/about/train.jpeg" />
            <figcaption style="color: #FF7F50">Korea 2023 Train</figcaption>
        </figure>
        <figure class="pic2">
            <img src="{{site.baseurl}}/images/about/alley.jpeg" />
            <figcaption style="color: #FF7F50">Korea 2023 Alley</figcaption>
        </figure>
        <figure class="pic3">
            <img src="{{site.baseurl}}/images/about/cat.JPG" />
            <figcaption style="color: #FF7F50">Cat</figcaption>
        </figure>
        <figure class="pic4">
            <img src="{{site.baseurl}}/images/about/gokart.jpeg" />
            <figcaption style="color: #FF7F50">Utah 2024 Go Kart</figcaption>
        </figure>
        <figure class="pic5">
            <img src="{{site.baseurl}}/images/about/dave.JPG" />
            <figcaption style="color: #FF7F50">2024 Dave and Busters</figcaption>
        </figure>
        <figure class="pic6">
            <img src="{{site.baseurl}}/images/about/korea.jpeg" />
            <figcaption style="color: #FF7F50">Korea 2023 Walk</figcaption>
        </figure>
        <figure class="pic7">
            <img src="{{site.baseurl}}/images/about/hike.JPG" />
            <figcaption style="color: #FF7F50">Utah 2024 Hike</figcaption>
        </figure>


</div>



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
            "I love listening to music",
            "I hit top 175 in Valorant NA",
            "I have a ragdoll cat named Miko",
            "I tore my ACL in 5th grade(not so fun)",
            "I've played with TenZ and Shroud(name a famous Valorant player and I've played with them) "
        ];

        const factDisplay = document.getElementById('factDisplay');
        const generateBtn = document.getElementById('generateBtn');

        generateBtn.addEventListener('click', function() {
            const randomIndex = Math.floor(Math.random() * facts.length);
            factDisplay.innerHTML = facts[randomIndex];
          
        });
    });
</script>
