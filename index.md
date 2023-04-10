<html>
    <h1 class="main-page">Build Your own PC!</h1>
    <hr>
    <style>
        .main-page{
            text-align: center;
            color: #000000;
        }
    </style>
<div class="main-page">
    <div id="start-page" class="text-style">
        <p>Build your own custom PC!</p>
        <button class="button_css" id="start-button" onclick="startSpecs()">Start</button>
    </div>
    <div id="select-cpu" class="text-style">
        <p>Please select your CPU:</p>
        <button class="button_css" onclick="lowTier(1)">Intel Core i3(Low tier)</button>
        <button class="button_css" onclick="medTier(1)">Intel Core i5(Medium tier)</button>
        <button class="button_css" onclick="highTier(1)">Intel Core i7(High tier)</button>
        <button class="button_css" onclick="veryhighTier(1)">Intel Core i9(Very high tier)</button>
    </div>
    <div id="select-gpu" class="text-style">
        <p>Please select your GPU:</p>
        <button class="button_css" onclick="lowTier(2)">Intel Iris Xe(Low tier)</button>
        <button class="button_css" onclick="medTier(2)">Nvidia GeForce RTX 3050(Medium tier)</button>
        <button class="button_css" onclick="highTier(2)">Nvidia GeForce RTX 4070(High tier)</button>
    </div>
    <div id="select-storage" class="text-style">
        <p>Please select your storage:</p>
        <button class="button_css" onclick="lowTier(3)">512 GB(Low tier)</button>
        <button class="button_css" onclick="medTier(3)">1 TB(Medium tier)</button>
        <button class="button_css" onclick="highTier(3)">2 TB(High tier)</button>
    </div>
    <div id="select-memory" class="text-style">
        <p>Please select your memory:</p>
        <button class="button_css" onclick="lowTier(4)">8 GB(Low tier)</button>
        <button class="button_css" onclick="medTier(4)">16 GB(Medium tier)</button>
        <button class="button_css" onclick="highTier(4)">32 GB(High tier)</button>
        <button class="button_css" onclick="veryhighTier(4)">64 GB(Very high tier)</button>
    </div>
    <div id="select-display" class="text-style">
        <p>Please select your display:</p>
        <button class="button_css" onclick="lowTier(5)">HD(Low tier)</button>
        <button class="button_css" onclick="medTier(5)">Full HD(Medium tier)</button>
        <button class="button_css" onclick="highTier(5)">Quad HD(High tier)</button>
        <button class="button_css" onclick="veryhighTier(5)">Ultra HD/4K(Very high tier)</button>
    </div>
    <div id="end-screen" class="text-style">
        <h2>Thank you for customizing your PC!</h2>
        <h3>Based on your chosen specifications, the estimated price of your PC is: <span id="price">0</span>
        <p id="price-comment">comment</p>
        <p>Here's the specifications your chose for your PC:</p>
        <p id="customization-list">list</p>
        <p>Press restart below to customize another PC:</p>
        <button id="restart-button" onclick="restartCustomization()">Restart</button>
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

    homeScreen.style.display = "block";
    cpuScreen.style.display = "none";
    gpuScreen.style.display = "none";
    storageScreen.style.display = "none";
    memoryScreen.style.display = "none";
    displayScreen.style.display = "none";
    finishScreen.style.display = "none";

    const price_display = document.getElementById("price");
    const price_comment_display = document.getElementById("price-comment");
    const displaySpecsList = document.getElementById("customization-list");
    const restart = document.getElementById("restart-button");

    var priceSum = 0;
    const specsList = [];

    function startSpecs() {
        homeScreen.style.display = "none";
        cpuScreen.style.display = "block";
    }

    function lowTier(pageNumber) {
        priceSum = priceSum + 150;
        if(pageNumber === 1){
            cpuScreen.style.display === "none";
            gpuScreen.style.display === "block";
            specsList.push("Intel Core i3");
        }
        if(pageNumber === 2){
            gpuScreen.style.display === "none";
            storageScreen.style.display === "block";
            specsList.push("Intel Iris Xe");
        }
        if(pageNumber === 3){
            storageScreen.style.display === "none";
            memoryScreen.style.display === "block";
            specsList.push("512 GB");
        }
        if(pageNumber === 4){
            memoryScreen.style.display === "none";
            displayScreen.style.display === "block";
            specsList.push("8 GB");
        }
        if(pageNumber === 5){
            displayScreen.style.display === "none";
            finishScreen.style.display === "block";
            specsList.push("HD");
        }
    }

    function medTier(pageNumber) {
        priceSum = priceSum + 300;
        if(pageNumber === 1){
            cpuScreen.style.display === "none";
            gpuScreen.style.display === "block";
            specsList.push("Intel Core i5");
        }
        if(pageNumber === 2){
            gpuScreen.style.display === "none";
            storageScreen.style.display === "block";
            specsList.push("Nvidia GeForce RTX 3050");
        }
        if(pageNumber === 3){
            storageScreen.style.display === "none";
            memoryScreen.style.display === "block";
            specsList.push("1 TB");
        }
        if(pageNumber === 4){
            memoryScreen.style.display === "none";
            displayScreen.style.display === "block";
            specsList.push("16 GB");
        }
        if(pageNumber === 5){
            displayScreen.style.display === "none";
            finishScreen.style.display === "block";
            specsList.push("Full HD");
        }
    }

    function highTier(pageNumber) {
        priceSum = priceSum + 600;
        if(pageNumber === 1){
            cpuScreen.style.display === "none";
            gpuScreen.style.display === "block";
            specsList.push("Intel Core i7");
        }
        if(pageNumber === 2){
            gpuScreen.style.display === "none";
            storageScreen.style.display === "block";
            specsList.push("Nvidia GeForce RTX 4070");
        }
        if(pageNumber === 3){
            storageScreen.style.display === "none";
            memoryScreen.style.display === "block";
            specsList.push("2 TB");
        }
        if(pageNumber === 4){
            memoryScreen.style.display === "none";
            displayScreen.style.display === "block";
            specsList.push("32 GB");
        }
        if(pageNumber === 5){
            displayScreen.style.display === "none";
            finishScreen.style.display === "block";
            specsList.push("Quad HD");
        }
    }

    function veryhighTier(pageNumber) {
        priceSum = priceSum + 800;
        if(pageNumber === 1){
            cpuScreen.style.display === "none";
            gpuScreen.style.display === "block";
            specsList.push("Intel Core i9");
        }
        if(pageNumber === 4){
            memoryScreen.style.display === "none";
            displayScreen.style.display === "block";
            specsList.push("64 GB");
        }
        if(pageNumber === 5){
            displayScreen.style.display === "none";
            finishScreen.style.display === "block";
            specsList.push("Ultra HD/4K");
        }
    }

    if(finishScreen.style.display === "block"){
        price_display.innerHTML = string(priceSum);
        if(priceSum <= 1000){
            price_comment_display.innerHTML = "The PC with your specifications is relatively cheap!";
        }
        if(priceSum <= 1500 && priceSum > 1000){
            price_comment_display.innerHTML = "The PC with your specifications is at a moderate price.";
        }
        if(priceSum > 1500){
            price_comment_display.innerHTML = "The PC with your specifications is pretty expensive. Make sure to pay attention to your budget!";
        }
        for(let i=0; i < specsList.length; i++){
            displaySpecsList.innerHTML = specsList[i] + "<br>";
        }
    }

    function restartCustomization() {
        homeScreen.style.display = "block";
        cpuScreen.style.display = "none";
        gpuScreen.style.display = "none";
        storageScreen.style.display = "none";
        memoryScreen.style.display = "none";
        displayScreen.style.display = "none";
        finishScreen.style.display = "none";
        priceSum = 0;

        let x = specsList.length;
        while(x > -1){
            specsList.pop();
        }
    }
</script>
</html>