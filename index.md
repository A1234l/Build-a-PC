<!-- The website that I created has been built using the website template from Mr. Mortensen's repository: https://github.com/jm1021/leuck_reunion.
The Architect theme for my website has been used. Credits to the Architect theme repository: https://github.com/pages-themes/architect.
Another credits to Intel and Nvidia for the CPU and GPU products that I included in the code. -->
<html>
    <h1 class="main-page">Build Your own PC!</h1>
    <hr>
    <style>
        .main-page{
            text-align: center;
            color: #000000;
        }
        .button_css{
            background-color: #b4e612;
            margin-bottom: 50px;
            padding-top: 20px;
            padding-bottom: 20px;
            padding-right: 30px;
            padding-left: 30px;
            transition: all 0.6s;
            border-width: 1px;
        }
        .button_css:hover{
            background-color: #5b6342;
            color: #babdd9;
        }
        .start-end-button{
            background-color: #d96262;
            margin-bottom: 50px;
            padding-top: 15px;
            padding-bottom: 15px;
            padding-right: 40px;
            padding-left: 40px;
            transition: all 0.6s;
            border-width: 3px;
        }
        .start-end-button:hover{
            background-color: #888a4e;
            color: #abd6d1;
        }
        #price-comment{
            background-color: #f2ef35;
            border-width: 5px;
        }
    </style>
<body>
<div class="main-page">
    <div id="start-page" class="text-style">
        <p>Build your own custom PC!</p>
        <button class="start-end-button" id="start-button" onclick="startSpecs()">Start</button>
    </div>
    <div id="select-cpu" class="text-style">
        <p>Please select your CPU:</p>
        <button class="button_css" onclick="lowTier(1)">Intel Core i3(Low tier)</button>
        <br>
        <button class="button_css" onclick="medTier(1)">Intel Core i5(Medium tier)</button>
        <br>
        <button class="button_css" onclick="highTier(1)">Intel Core i7(High tier)</button>
        <br>
        <button class="button_css" onclick="veryhighTier(1)">Intel Core i9(Very high tier)</button>
    </div>
    <div id="select-gpu" class="text-style">
        <p>Please select your GPU:</p>
        <button class="button_css" onclick="lowTier(2)">Intel Iris Xe(Low tier)</button>
        <br>
        <button class="button_css" onclick="medTier(2)">Nvidia GeForce RTX 3050(Medium tier)</button>
        <br>
        <button class="button_css" onclick="highTier(2)">Nvidia GeForce RTX 4070(High tier)</button>
    </div>
    <div id="select-storage" class="text-style">
        <p>Please select your storage:</p>
        <button class="button_css" onclick="lowTier(3)">512 GB(Low tier)</button>
        <br>
        <button class="button_css" onclick="medTier(3)">1 TB(Medium tier)</button>
        <br>
        <button class="button_css" onclick="highTier(3)">2 TB(High tier)</button>
    </div>
    <div id="select-memory" class="text-style">
        <p>Please select your memory:</p>
        <button class="button_css" onclick="lowTier(4)">8 GB(Low tier)</button>
        <br>
        <button class="button_css" onclick="medTier(4)">16 GB(Medium tier)</button>
        <br>
        <button class="button_css" onclick="highTier(4)">32 GB(High tier)</button>
        <br>
        <button class="button_css" onclick="veryhighTier(4)">64 GB(Very high tier)</button>
    </div>
    <div id="select-display" class="text-style">
        <p>Please select your display:</p>
        <button class="button_css" onclick="lowTier(5)">HD(Low tier)</button>
        <br>
        <button class="button_css" onclick="medTier(5)">Full HD(Medium tier)</button>
        <br>
        <button class="button_css" onclick="highTier(5)">Quad HD(High tier)</button>
        <br>
        <button class="button_css" onclick="veryhighTier(5)">Ultra HD/4K(Very high tier)</button>
    </div>
    <div id="end-screen" class="text-style">
        <p>Thank you for customizing your PC!</p>
        <p>Based on your chosen specifications, the estimated price of your PC is: <strong><span id="price">0</span></strong></p>
        <p><span id="price-comment"></span></p>
        <p>Here's the specifications you chose for your PC:</p>
        <p id="customization-list">list should display here</p>
        <p>Press restart below to customize another PC:</p>
        <button class="start-end-button" id="restart-button" onclick="restartCustomization()">Restart</button>
    </div>
</div>

<script>
    const homeScreen = document.getElementById("start-page");
    const cpuScreen = document.getElementById("select-cpu");
    const gpuScreen = document.getElementById("select-gpu");
    const storageScreen = document.getElementById("select-storage");
    const memoryScreen = document.getElementById("select-memory");
    const displayScreen = document.getElementById("select-display");

    const finishScreen = document.getElementById("end-screen");
    const price_display = document.getElementById("price");
    const price_comment_display = document.getElementById("price-comment");
    const displaySpecsList = document.getElementById("customization-list");
    const restart = document.getElementById("restart-button");

    homeScreen.style.display = "block";
    cpuScreen.style.display = "none";
    gpuScreen.style.display = "none";
    storageScreen.style.display = "none";
    memoryScreen.style.display = "none";
    displayScreen.style.display = "none";
    finishScreen.style.display = "none";

    var priceSum = 0;
    var specsList = [];

    console.log(specsList);
    
    // Function starts the customization form, called by start button
    function startSpecs() {
        homeScreen.style.display = "none";
        cpuScreen.style.display = "block";
    }

    // Function is called for all low tier selections
    function lowTier(pageNumber) {
        priceSum = priceSum + 150;
        if(pageNumber === 1){
            cpuScreen.style.display = "none";
            gpuScreen.style.display = "block";
            specsList.push("CPU: Intel Core i3");
        } else if(pageNumber === 2){
            gpuScreen.style.display = "none";
            storageScreen.style.display = "block";
            specsList.push("GPU: Intel Iris Xe");
        } else if(pageNumber === 3){
            storageScreen.style.display = "none";
            memoryScreen.style.display = "block";
            specsList.push("Storage: 512 GB");
        } else if(pageNumber === 4){
            memoryScreen.style.display = "none";
            displayScreen.style.display = "block";
            specsList.push("Memory: 8 GB");
        } else if(pageNumber === 5){
            displayScreen.style.display = "none";
            finishScreen.style.display = "block";
            specsList.push("Display: HD");
            checkFinishDisplay();
        }
    }

    // Function is called for all medium tier selections
    function medTier(pageNumber) {
        priceSum = priceSum + 300;
        if(pageNumber === 1){
            cpuScreen.style.display = "none";
            gpuScreen.style.display = "block";
            specsList.push("CPU: Intel Core i5");
        } else if(pageNumber === 2){
            gpuScreen.style.display = "none";
            storageScreen.style.display = "block";
            specsList.push("GPU: Nvidia GeForce RTX 3050");
        } else if(pageNumber === 3){
            storageScreen.style.display = "none";
            memoryScreen.style.display = "block";
            specsList.push("Storage: 1 TB");
        } else if(pageNumber === 4){
            memoryScreen.style.display = "none";
            displayScreen.style.display = "block";
            specsList.push("Memory: 16 GB");
        } else if(pageNumber === 5){
            displayScreen.style.display = "none";
            finishScreen.style.display = "block";
            specsList.push("Display: Full HD");
            checkFinishDisplay();
        }
    }

    // Function is called for all high tier selections
    function highTier(pageNumber) {
        priceSum = priceSum + 600;
        if(pageNumber === 1){
            cpuScreen.style.display = "none";
            gpuScreen.style.display = "block";
            specsList.push("CPU: Intel Core i7");
        } else if(pageNumber === 2){
            gpuScreen.style.display = "none";
            storageScreen.style.display = "block";
            specsList.push("GPU: Nvidia GeForce RTX 4070");
        } else if(pageNumber === 3){
            storageScreen.style.display = "none";
            memoryScreen.style.display = "block";
            specsList.push("Storage: 2 TB");
        } else if(pageNumber === 4){
            memoryScreen.style.display = "none";
            displayScreen.style.display = "block";
            specsList.push("Memory: 32 GB");
        } else if(pageNumber === 5){
            displayScreen.style.display = "none";
            finishScreen.style.display = "block";
            specsList.push("Display: Quad HD");
            checkFinishDisplay();
        }
    }

    // Function is called for all very high tier selections, only available for some configurations
    function veryhighTier(pageNumber) {
        priceSum = priceSum + 800;
        if(pageNumber === 1){
            cpuScreen.style.display = "none";
            gpuScreen.style.display = "block";
            specsList.push("CPU: Intel Core i9");
        } else if(pageNumber === 4){
            memoryScreen.style.display = "none";
            displayScreen.style.display = "block";
            specsList.push("Memory: 64 GB");
        } else if(pageNumber === 5){
            displayScreen.style.display = "none";
            finishScreen.style.display = "block";
            specsList.push("Display: Ultra HD/4K");
            checkFinishDisplay();
        }
    }

    // Checks if user is on finish screen and displays necessary info on finish screen
    function checkFinishDisplay(){
        if (finishScreen.style.display === "block") {
            // Display price
            price_display.innerHTML = priceSum + " dollars";
            // Display comment
            if(priceSum <= 1000){
                price_comment_display.innerHTML = "The PC with your specifications is relatively cheap!";
            } else if(priceSum <= 1500 && priceSum > 1000){
                price_comment_display.innerHTML = "The PC with your specifications is at a moderate price.";
            } else if(priceSum > 1500){
                price_comment_display.innerHTML = "The PC with your specifications is pretty expensive. Make sure to pay attention to your budget!";
            }
            // Display specifications chosen by user
            let listDisplay = "";
            for (let i = 0; i < specsList.length; i++) {
                listDisplay = listDisplay + specsList[i] + "<br>";
            }
            displaySpecsList.innerHTML = listDisplay;
        }
    }


    // Resets all data and returns to start screen, called by restart button
    function restartCustomization() {
        homeScreen.style.display = "block";
        cpuScreen.style.display = "none";
        gpuScreen.style.display = "none";
        storageScreen.style.display = "none";
        memoryScreen.style.display = "none";
        displayScreen.style.display = "none";
        finishScreen.style.display = "none";

        priceSum = 0;
        specsList = [];
    }
</script>
</body>
</html>