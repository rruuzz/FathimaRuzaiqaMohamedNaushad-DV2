<html>
<head>
<title>Global Wastage Analysis</title>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<script src="https://cdn.jsdelivr.net/npm/vega@5.25.0"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5.16.0"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6.22.2"></script>
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<script type="text/javascript" src="https://gc.kis.v2.scr.kaspersky-labs.com/FD126C42-EBFA-4E12-B309-BB3FDD723AC1/main.js?attr=D9QkURtyIKDD3hI0A36TXe2bGa35n1CunCDCLO6RvSmLxJZKByvPdIov20uxjqkestKw_inSdH4IltD1c_rFSf5mShYaanORxjbm5ZD-DNg" charset="UTF-8"></script><link rel="stylesheet" crossorigin="anonymous" href="https://gc.kis.v2.scr.kaspersky-labs.com/E3E8934C-235A-4B0E-825A-35A08381A191/abn/main.css?attr=aHR0cHM6Ly93d3cudzNzY2hvb2xzLmNvbS93M2Nzcy90cnl3M2Nzc190ZW1wbGF0ZXNfcGhvdG8uaHRt"/><style>
body,h1 {font-family: "Montserrat", sans-serif}
img {margin-bottom: -7px}
.w3-row-padding img {margin-bottom: 12px}
.my-element {background-color: #E0ECF3}
</style>
<script>Idioms.js</script>
</head>
<body>


<!-- !PAGE CONTENT! -->
<div class="w3-content" style="max-width:1500px">

<!-- Header -->
<div class="my-element">
<div class="w3-clear"></div>
<header class="w3-center w3-margin-bottom">
  <h1><b>Global Wastage Analysis</b></h1>
  <p><b>A data visualization representing analysis of gloabal wastage</b></p>
  <p class="w3-padding-16"><button class="w3-button w3-black" onclick="myFunction()">Toggle Grid Padding</button></p>
</header>
</div>

<!-- Photo Grid -->
<div class="w3-row" id="myGrid" style="margin-bottom:128px">
    <div class="w3-center w3-margin-bottom">
        <b>   Data on solid waste management from throughout the world is compiled. This database contains the statistics gathered during the endeavor, which span virtually all countries and over 330 cities. The metrics contain information on all aspects of the waste management value chain, such as trash generation, composition, collection, and disposal, as well as user.     </b>
    </div>
        
    <div class = "w3-container w3-padding-20 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div class="w3-center w3-margin-bottom">
        
        <img src="C:\Users\HP\Documents\GitHub\FathimaRuzaiqaMohamedNaushad-DV2\mapvis.png" style="width:100%">
        <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
            <b>~ </b>
        </div>
        <b>The above graph represents the the GDP of each country in the for of a Chloropeth Map. </b>
    </div>
    
  <div class="w3-half">
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div id="chart1" style="width: 50%; height: 400px">
    </div>
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div class="w3-center w3-margin-bottom">
        <b> The above bar chart represents Total MSW generated yearly in each region</b>
    </div>
  </div>

  <div class="w3-half">
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
   
    <img src="C:\Users\HP\Documents\GitHub\FathimaRuzaiqaMohamedNaushad-DV2\scatVis.png" style="width:100%">
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div class="w3-center w3-margin-bottom">
        <b> The above Scatter graph representsthe correlation between the Total MSW generated yearly agaisnt the Total Waste collection.</b>
    </div>
</div>

<div>
    <img src="C:\Users\HP\Documents\GitHub\FathimaRuzaiqaMohamedNaushad-DV2\visualizationBub.png" style="width:100%">
    <div class="w3-center w3-margin-bottom">
        <b> The above Bubble plot representsthe data of each country and its corresponging population.</b>
    </div>
</div>


</div>

<!-- End Page Content -->
</div>

<!-- Footer -->
<footer class="w3-container w3-padding-30 w3-light-grey w3-center w3-opacity w3-xlarge" style="margin-top:128px"> 
  
  <p class="w3-medium">Designed by Fathima Ruzaiqa Naushad</p>
</footer>
 
<script>
// Toggle grid padding
function myFunction() {
  var x = document.getElementById("myGrid");
  if (x.className === "w3-row") {
    x.className = "w3-row-padding";
  } else { 
    x.className = x.className.replace("w3-row-padding", "w3-row");
  }
}

// Open and close sidebar
function w3_open() {
  document.getElementById("mySidebar").style.width = "100%";
  document.getElementById("mySidebar").style.display = "block";
}

function w3_close() {
  document.getElementById("mySidebar").style.display = "none";
}
</script>

</body>
</html>
