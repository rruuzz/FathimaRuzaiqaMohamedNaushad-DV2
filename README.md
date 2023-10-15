
<!DOCTYPE html>
<html>


  <head>
  <title>Global Wastage Analysis</title>

  <script type="text/javascript" charset="UTF-8"></script>
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Import Vega and Vega Lite -->
  <script src="https://cdn.jsdelivr.net/npm/vega@5.20.2"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-lite@5.1.0"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-embed@6.17.0"></script>

  <!-- Import Google fonts -->
  <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Oswald">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans&display=swap" rel="stylesheet">

  <!-- Import pure.css -->
  <link rel="stylesheet" href="https://unpkg.com/purecss@2.0.3/build/pure-min.css"
  integrity="sha384-cg6SkqEOCV1NbJoCu11+bm0NvBRc8IYLRGXkmNrqUBfTjmMYwNKPWBTIKyw9mHNJ" crossorigin="anonymous">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Import style css file -->
  <link rel="stylesheet" type="text/css" href="styles.css" media="all">

</head>
<body>

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
    <div id="bar_chart class="vis-container">
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

<script type="text/javascript">

  var vis1 = "Idioms/Bar01.json";
  vegaEmbed("#vis", spec, {mode: "vega-lite"}).then(console.log).catch(console.warn);

  var vis2 = "Idioms/Bubble.json";
  vegaEmbed('#bubble_chart', vis2).then(function(result) {
  // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);

  var vis3 = "Idioms/Map.json";
  vegaEmbed('#chloropeth_map', vis3).then(function(result) {
  // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);

  var vis4 = "Idioms/Scatter01.json";
  vegaEmbed('#scatter_plot', vis4).then(function(result) {
  // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);

  var vis5 = "Idioms/Scatter02.json";
  vegaEmbed('#scatter_plot', vis5).then(function(result) {
  // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
</script>


</body>
</html>
