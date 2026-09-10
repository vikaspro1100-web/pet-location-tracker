<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>PetSafe | Smart Pet Identification</title>

    <!-- QR Code Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background: #f5f8f7;
            color: #17221f;
        }

        /* NAVBAR */

        nav {
            background: white;
            padding: 18px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 15px rgba(0,0,0,0.06);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 24px;
            font-weight: 800;
        }

        .logo span {
            color: #18a875;
        }

        nav button {
            border: none;
            background: #18a875;
            color: white;
            padding: 10px 18px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
        }

        /* HERO */

        .hero {
            min-height: 430px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 60px 8%;
            gap: 40px;
            background: linear-gradient(135deg, #eafff5, #f5fbff);
        }

        .hero-text {
            max-width: 600px;
        }

        .badge {
            display: inline-block;
            background: #d5f8e9;
            color: #08734c;
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: bold;
            margin-bottom: 18px;
        }

        .hero h1 {
            font-size: 52px;
            line-height: 1.05;
            margin-bottom: 20px;
        }

        .hero h1 span {
            color: #18a875;
        }

        .hero p {
            color: #52615c;
            font-size: 17px;
            line-height: 1.6;
            margin-bottom: 25px;
        }

        .hero-btn {
            display: inline-block;
            background: #18a875;
            color: white;
            text-decoration: none;
            padding: 14px 25px;
            border-radius: 12px;
            font-weight: bold;
            margin-right: 10px;
        }

        .hero-btn.secondary {
            background: white;
            color: #18a875;
            border: 1px solid #18a875;
        }

        .pet-icon {
            width: 260px;
            height: 260px;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 130px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.08);
        }

        /* SECTIONS */

        section {
            padding: 60px 8%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 40px;
        }

        .section-title h2 {
            font-size: 32px;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #68746f;
        }

        /* PET CARD */

        .pet-card {
            max-width: 900px;
            margin: auto;
            background: white;
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 10px 35px rgba(0,0,0,0.07);
        }

        .pet-top {
            display: flex;
            gap: 25px;
            align-items: center;
            margin-bottom: 30px;
        }

        .pet-photo {
            width: 130px;
            height: 130px;
            border-radius: 20px;
            background: #e8f8f1;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 70px;
        }

        .pet-info h2 {
            font-size: 30px;
            margin-bottom: 8px;
        }

        .pet-info p {
            color: #68746f;
            margin: 5px 0;
        }

        .verified {
            display: inline-block;
            background: #e1f8ed;
            color: #118156;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
            margin-top: 8px;
        }

        /* INFORMATION GRID */

        .info-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .info-box {
            background: #f7faf9;
            border-radius: 15px;
            padding: 18px;
        }

        .info-box small {
            color: #78847f;
            display: block;
            margin-bottom: 6px;
        }

        .info-box strong {
            font-size: 17px;
        }

        /* LOCATION */

        .location-card {
            max-width: 900px;
            margin: auto;
            background: #17221f;
            color: white;
            border-radius: 25px;
            padding: 30px;
        }

        .location-card h3 {
            font-size: 25px;
            margin-bottom: 10px;
        }

        .location-card p {
            color: #cbd6d2;
            line-height: 1.6;
        }

        .location-display {
            background: rgba(255,255,255,0.08);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
        }

        .location-display strong {
            font-size: 18px;
        }

        .location-buttons {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .location-buttons button,
        .hospital-btn {
            border: none;
            padding: 12px 18px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        .primary {
            background: #18a875;
            color: white;
        }

        .light {
            background: white;
            color: #17221f;
        }

        /* HOSPITALS */

        .hospital-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            max-width: 1000px;
            margin: auto;
        }

        .hospital {
            background: white;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.06);
        }

        .hospital-icon {
            font-size: 35px;
            margin-bottom: 12px;
        }

        .hospital h3 {
            margin-bottom: 8px;
        }

        .hospital p {
            color: #69756f;
            font-size: 14px;
            line-height: 1.5;
            margin-bottom: 15px;
        }

        .hospital-btn {
            background: #e5f8f0;
            color: #08734c;
            width: 100%;
        }

        /* QR */

        .qr-section {
            background: #eafff5;
        }

        .qr-container {
            max-width: 900px;
            margin: auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            align-items: center;
        }

        .qr-card {
            background: white;
            padding: 30px;
            border-radius: 25px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.06);
        }

        #qrcode {
            display: flex;
            justify-content: center;
            margin: 20px 0;
        }

        .qr-card button {
            background: #18a875;
            border: none;
            color: white;
            padding: 12px 20px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        .qr-explanation h2 {
            font-size: 32px;
            margin-bottom: 15px;
        }

        .qr-explanation p {
            color: #5d6964;
            line-height: 1.7;
        }

        /* OWNER */

        .owner-card {
            max-width: 900px;
            margin: auto;
            background: white;
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.06);
        }

        .owner-card h2 {
            margin-bottom: 20px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        input,
        textarea {
            width: 100%;
            padding: 13px;
            border: 1px solid #dbe4df;
            border-radius: 10px;
            outline: none;
            margin-top: 6px;
        }

        textarea {
            min-height: 100px;
            resize: vertical;
        }

        label {
            font-weight: bold;
            font-size: 14px;
        }

        .full {
            grid-column: 1 / -1;
        }

        .save-btn {
            margin-top: 20px;
            border: none;
            background: #18a875;
            color: white;
            padding: 14px 25px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        /* HOW IT WORKS */

        .steps {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            max-width: 1000px;
            margin: auto;
        }

        .step {
            text-align: center;
            background: white;
            padding: 25px;
            border-radius: 20px;
            box-shadow: 0 7px 25px rgba(0,0,0,0.05);
        }

        .step-number {
            width: 50px;
            height: 50px;
            background: #18a875;
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 20px;
            font-weight: bold;
        }

        .step p {
            color: #69756f;
            line-height: 1.5;
            margin-top: 8px;
        }

        /* FOOTER */

        footer {
            background: #17221f;
            color: white;
            text-align: center;
            padding: 30px;
        }

        footer p {
            color: #b9c6c1;
            margin-top: 8px;
        }

        /* RESPONSIVE */

        @media(max-width: 750px) {

            .hero {
                flex-direction: column;
                text-align: center;
            }

            .hero h1 {
                font-size: 38px;
            }

            .pet-icon {
                width: 190px;
                height: 190px;
                font-size: 90px;
            }

            .info-grid,
            .form-grid,
            .qr-container {
                grid-template-columns: 1fr;
            }

            .hospital-grid,
            .steps {
                grid-template-columns: 1fr;
            }

            .pet-top {
                flex-direction: column;
                text-align: center;
            }
        }

    </style>
</head>

<body>

<!-- NAVIGATION -->

<nav>
    <div class="logo">🐾 Pet<span>Safe</span></div>

    <button onclick="document.getElementById('pet').scrollIntoView()">
        View Pet
    </button>
</nav>


<!-- HERO -->

<header class="hero">

    <div class="hero-text">

        <div class="badge">
            SMART PET IDENTIFICATION SYSTEM
        </div>

        <h1>
            Keep every pet<br>
            <span>safe & connected.</span>
        </h1>

        <p>
            A QR-based pet identification system that helps
            people identify a lost pet, contact its owner,
            find its last-seen location and locate nearby
            veterinary hospitals.
        </p>

        <a href="#pet" class="hero-btn">
            View Pet Profile
        </a>

        <a href="#qr" class="hero-btn secondary">
            Generate QR
        </a>

    </div>

    <div class="pet-icon">
        🐕
    </div>

</header>


<!-- PET PROFILE -->

<section id="pet">

    <div class="section-title">
        <h2>🐾 Pet Profile</h2>
        <p>Important information available after scanning the QR code</p>
    </div>

    <div class="pet-card">

        <div class="pet-top">

            <div class="pet-photo">
                🐶
            </div>

            <div class="pet-info">

                <h2 id="displayPetName">Buddy</h2>

                <p>
                    <b>Breed:</b>
                    <span id="displayBreed">Golden Retriever</span>
                </p>

                <p>
                    <b>Age:</b>
                    <span id="displayAge">3 Years</span>
                </p>

                <span class="verified">
                    ✓ VERIFIED PET PROFILE
                </span>

            </div>

        </div>


        <div class="info-grid">

            <div class="info-box">
                <small>Pet ID</small>
                <strong id="displayPetId">PET-2026-001</strong>
            </div>

            <div class="info-box">
                <small>Gender</small>
                <strong id="displayGender">Male</strong>
            </div>

            <div class="info-box">
                <small>Owner</small>
                <strong id="displayOwner">Vikas</strong>
            </div>

            <div class="info-box">
                <small>Contact</small>
                <strong id="displayPhone">+91 XXXXX XXXXX</strong>
            </div>

        </div>

    </div>

</section>


<!-- OWNER INFORMATION -->

<section>

    <div class="section-title">
        <h2>👤 Owner Information</h2>
        <p>Contact information for returning a lost pet</p>
    </div>

    <div class="owner-card">

        <h2>Pet Registration</h2>

        <div class="form-grid">

            <div>
                <label>Pet Name</label>
                <input id="petName" value="Buddy">
            </div>

            <div>
                <label>Breed</label>
                <input id="breed" value="Golden Retriever">
            </div>

            <div>
                <label>Age</label>
                <input id="age" value="3 Years">
            </div>

            <div>
                <label>Gender</label>
                <input id="gender" value="Male">
            </div>

            <div>
                <label>Owner Name</label>
                <input id="owner" value="Vikas">
            </div>

            <div>
                <label>Contact Number</label>
                <input id="phone" value="+91 XXXXX XXXXX">
            </div>

            <div class="full">
                <label>Important Information</label>
                <textarea id="notes">Friendly dog. Please contact the owner if found.</textarea>
            </div>

        </div>

        <button class="save-btn" onclick="savePet()">
            💾 Save Pet Information
        </button>

    </div>

</section>


<!-- LOCATION -->

<section>

    <div class="section-title">

        <h2>📍 Pet Location</h2>

        <p>
            Last known location of the pet
        </p>

    </div>


    <div class="location-card">

        <h3>Last Seen Location</h3>

        <p>
            The owner can update the pet's location using
            the phone's GPS. Location access requires permission.
        </p>

        <div class="location-display">

            <strong id="locationText">
                📍 Demo Location: Bengaluru, Karnataka
            </strong>

            <br><br>

            <small id="coordinates">
                Coordinates: 12.9716, 77.5946
            </small>

        </div>


        <div class="location-buttons">

            <button class="primary" onclick="getLocation()">
                📍 Use My Current Location
            </button>

            <button class="light" onclick="openMap()">
                🗺️ Open in Google Maps
            </button>

        </div>

    </div>

</section>


<!-- HOSPITALS -->

<section>

    <div class="section-title">

        <h2>🏥 Nearby Veterinary Hospitals</h2>

        <p>
            Quickly find veterinary care for the pet
        </p>

    </div>


    <div class="hospital-grid">

        <div class="hospital">

            <div class="hospital-icon">
                🏥
            </div>

            <h3>Nearby Veterinary Hospital</h3>

            <p>
                Find veterinary hospitals close to
                the pet's current location.
            </p>

            <button
                class="hospital-btn"
                onclick="findHospitals()">

                Find Nearest Hospital

            </button>

        </div>


        <div class="hospital">

            <div class="hospital-icon">
                🩺
            </div>

            <h3>Pet Emergency Care</h3>

            <p>
                Search Google Maps for emergency
                veterinary services near you.
            </p>

            <button
                class="hospital-btn"
                onclick="findHospitals()">

                Find Emergency Care

            </button>

        </div>


        <div class="hospital">

            <div class="hospital-icon">
                ❤️
            </div>

            <h3>Pet Health Support</h3>

            <p>
                Quickly access nearby animal clinics
                when a pet needs medical attention.
            </p>

            <button
                class="hospital-btn"
                onclick="findHospitals()">

                Find Pet Clinic

            </button>

        </div>

    </div>

</section>


<!-- QR CODE -->

<section class="qr-section" id="qr">

    <div class="qr-container">

        <div class="qr-card">

            <h2>🔳 Pet QR Code</h2>

            <p>
                Scan this QR code to open the PetSafe
                pet identification page.
            </p>

            <div id="qrcode"></div>

            <button onclick="generateQR()">
                Generate QR Again
            </button>

        </div>


        <div class="qr-explanation">

            <h2>
                One scan can help bring a pet home.
            </h2>

            <p>
                The QR code can be attached to a pet's
                collar. If someone finds the pet, they
                can scan the code using a smartphone and
                view the pet profile and contact information.
            </p>

            <br>

            <p>
                <b>Privacy:</b> Only information that the
                owner chooses to publish should be displayed.
                Avoid publishing a home address or other
                sensitive information.
            </p>

        </div>

    </div>

</section>


<!-- HOW IT WORKS -->

<section>

    <div class="section-title">

        <h2>How PetSafe Works</h2>

        <p>
            Three simple steps
        </p>

    </div>


    <div class="steps">

        <div class="step">

            <div class="step-number">
                1
            </div>

            <h3>Scan QR</h3>

            <p>
                A person finds a lost pet and scans
                the QR code on its collar.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                2
            </div>

            <h3>View Profile</h3>

            <p>
                The pet's important information and
                owner's contact details are displayed.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                3
            </div>

            <h3>Get Help</h3>

            <p>
                The last-seen location and nearby
                veterinary hospitals can be accessed.
            </p>

        </div>

    </div>

</section>


<!-- FOOTER -->

<footer>

    <h3>🐾 PetSafe</h3>

    <p>
        Smart technology for safer pets.
    </p>

    <p>
        © 2026 PetSafe Exhibition Project
    </p>

</footer>


<script>

    /*
     * PET DATA
     */

    let latitude = 12.9716;
    let longitude = 77.5946;


    /*
     * SAVE PET INFORMATION
     */

    function savePet() {

        const petName =
            document.getElementById("petName").value;

        const breed =
            document.getElementById("breed").value;

        const age =
            document.getElementById("age").value;

        const gender =
            document.getElementById("gender").value;

        const owner =
            document.getElementById("owner").value;

        const phone =
            document.getElementById("phone").value;


        document.getElementById("displayPetName")
            .textContent = petName;

        document.getElementById("displayBreed")
            .textContent = breed;

        document.getElementById("displayAge")
            .textContent = age;

        document.getElementById("displayGender")
            .textContent = gender;

        document.getElementById("displayOwner")
            .textContent = owner;

        document.getElementById("displayPhone")
            .textContent = phone;


        localStorage.setItem(
            "petName",
            petName
        );

        localStorage.setItem(
            "breed",
            breed
        );

        localStorage.setItem(
            "age",
            age
        );

        localStorage.setItem(
            "gender",
            gender
        );

        localStorage.setItem(
            "owner",
            owner
        );

        localStorage.setItem(
            "phone",
            phone
        );


        alert("🐾 Pet information saved successfully!");
    }


    /*
     * LOAD SAVED DATA
     */

    function loadPet() {

        const fields = [
            "petName",
            "breed",
            "age",
            "gender",
            "owner",
            "phone"
        ];


        fields.forEach(function(field) {

            const saved =
                localStorage.getItem(field);

            if (saved) {

                document.getElementById(field)
                    .value = saved;
            }

        });


        const petName =
            localStorage.getItem("petName");

        const breed =
            localStorage.getItem("breed");

        const age =
            localStorage.getItem("age");

        const gender =
            localStorage.getItem("gender");

        const owner =
            localStorage.getItem("owner");

        const phone =
            localStorage.getItem("phone");


        if (petName)
            document.getElementById("displayPetName")
                .textContent = petName;

        if (breed)
            document.getElementById("displayBreed")
                .textContent = breed;

        if (age)
            document.getElementById("displayAge")
                .textContent = age;

        if (gender)
            document.getElementById("displayGender")
                .textContent = gender;

        if (owner)
            document.getElementById("displayOwner")
                .textContent = owner;

        if (phone)
            document.getElementById("displayPhone")
                .textContent = phone;
    }


    /*
     * GPS LOCATION
     */

    function getLocation() {

        if (!navigator.geolocation) {

            alert(
                "Your browser does not support location."
            );

            return;
        }


        document.getElementById("locationText")
            .textContent =
            "📍 Getting your current location...";


        navigator.geolocation.getCurrentPosition(

            function(position) {

                latitude =
                    position.coords.latitude;

                longitude =
                    position.coords.longitude;


                document.getElementById("locationText")
                    .textContent =
                    "📍 Current location captured";


                document.getElementById("coordinates")
                    .textContent =
                    "Coordinates: " +
                    latitude.toFixed(6) +
                    ", " +
                    longitude.toFixed(6);


                localStorage.setItem(
                    "latitude",
                    latitude
                );

                localStorage.setItem(
                    "longitude",
                    longitude
                );


                alert(
                    "📍 Location updated successfully!"
                );

            },

            function(error) {

                alert(
                    "Location permission was not given. " +
                    "Please allow location access."
                );

            }

        );

    }


    /*
     * OPEN LOCATION IN GOOGLE MAPS
     */

    function openMap() {

        const url =
            "https://www.google.com/maps/search/?api=1&query=" +
            latitude +
            "," +
            longitude;


        window.open(
            url,
            "_blank"
        );

    }


    /*
     * FIND NEAREST VETERINARY HOSPITAL
     */

    function findHospitals() {

        const url =
            "https://www.google.com/maps/search/veterinary+hospital+near+me";


        window.open(
            url,
            "_blank"
        );

    }


    /*
     * GENERATE QR CODE
     */

    function generateQR() {

        const qrContainer =
            document.getElementById("qrcode");


        qrContainer.innerHTML = "";


        new QRCode(

            qrContainer,

            {

                text: window.location.href,

                width: 180,

                height: 180

            }

        );

    }


    /*
     * LOAD SAVED LOCATION
     */

    function loadLocation() {

        const savedLat =
            localStorage.getItem("latitude");

        const savedLng =
            localStorage.getItem("longitude");


        if (savedLat && savedLng) {

            latitude =
                parseFloat(savedLat);

            longitude =
                parseFloat(savedLng);


            document.getElementById("locationText")
                .textContent =
                "📍 Saved Last-Seen Location";


            document.getElementById("coordinates")
                .textContent =
                "Coordinates: " +
                latitude.toFixed(6) +
                ", " +
                longitude.toFixed(6);

        }

    }


    /*
     * START WEBSITE
     */

    window.onload = function() {

        loadPet();

        loadLocation();

        generateQR();

    };

</script>

</body>
</html>
