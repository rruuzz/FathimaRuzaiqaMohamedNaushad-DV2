
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
<header class="w3-right w3-margin-bottom">
  <img background="header.jpg"></img>
  <h1>
    <b>Global Wastage Analysis</b></h1>
  <p><b>A data visualization representing analysis of gloabal wastage</b></p>
  <p class="w3-padding-16"><button class="w3-button w3-black" onclick="myFunction()">Toggle Grid Padding</button></p>
</header>
</div>

<!-- Photo Grid -->
<div class="w3-row" id="myGrid" style="margin-bottom:128px">
    <div class="w3-center w3-margin-bottom">
        <h4>   Data on solid waste management from throughout the world is compiled. This database contains the statistics gathered during the endeavor, which span virtually all countries and over 330 cities. The metrics contain information on all aspects of the waste management value chain, such as trash generation, composition, collection, and disposal, as well as user.     </h4>
    </div>
    <div id="map" class= "vis-container">
    <div class = "w3-container w3-padding-20 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div>
    <div class="w3-center w3-margin-bottom">
        <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
            <b>~ </b>
        </div>
        <b>The above graph represents the the GDP of each country in the for of a Chloropeth Map. </b>
    </div>
    
  <div class="w3-half">
    <div id="Bar" class="vis-container"></div>
  </div>
  <div>
    <div class="w3-center w3-margin-bottom">
        <b> The above bar chart represents Total MSW generated yearly in each region</b>
    </div>
  </div>

  <div class="w3-half">
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div id="Scatter01" class="w3-container"></div>
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div class="w3-center w3-margin-bottom">
        <b> The above Scatter graph representsthe correlation between the Total MSW generated yearly agaisnt the Total Waste collection.</b>
    </div>
</div>

<div class="w3-half">
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div id="Scatter02" class="vis-container"></div>
    <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div class="w3-center w3-margin-bottom">
        <b> The above Scatter graph representsthe correlation between the Total MSW generated yearly agaisnt the Total Waste collection.</b>
    </div>
</div>

<div>
  <div class = "w3-container w3-padding-10 w3-light-grey w3-center w3-opacity w3-xlarge">
        <b>~ </b>
    </div>
    <div id="Bubble" class="vis-container"></div>
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

  <script>
    const spec3 = {
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "title": "Population vs Total MSW",
  "data": {
    "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/country_level_data_0.csv"
  },
  "mark": "point",
  "transform": [
    {
      "calculate": "datum.population_population_number_of_people / 1000000",
      "as": "Population (in millions)"
    },
    {
      "calculate": "datum.total_msw_total_msw_generated_tons_year / 1000000",
      "as": "Total MSW Generated (in millions)"
    }
  ],
  "encoding": {
    "x": {
      "field": "Population (in millions)",
      "title": "Population (in millions)",
      "type": "quantitative",
      "scale": {"zero": false}
    },
    "y": {
      "field": "Total MSW Generated (in millions)",
      "type": "quantitative",
      "title": "Total MSW Generated (in millions)",
      "scale": {"zero": false}
    },
    "color": {"field": "region_id", "type": "nominal"},
    "tooltip": [
      {"field": "Total MSW Generated (in millions)"},
      {
        "field": "Population (in millions)",
        "title": "Population (in millions)",
        "type": "quantitative"
      }
    ]
  },
  "config": {}
};
vegaEmbed("Scatter02", spec3, {mode: "vega-lite"}).then(console.log).catch(console.warn);
</script>

<script>
  const spec1 = {
"$schema": "https://vega.github.io/schema/vega-lite/v5.json",
"title": {"text": "Total MSW per year"},
"data": {
  "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/country_level_data_0.csv"
},
"mark": {"type": "bar"},
"encoding": {
  "x": {"title": "Region Code", "field": "region_id", "type": "ordinal"},
  "y": {
    "aggregate": "sum",
    "field": "total_msw_total_msw_generated_tons_year",
    "title": "Total MSW Generated per Year"
  },
  "color": {"field": "region_id", "scale": {"scheme": "tableau10"}},
  "tooltip": [
    {"field": "region_id", "type": "ordinal"},
    {
      "field": "total_msw_total_msw_generated_tons_year",
      "type": "quantitative",
      "aggregate": "sum",
      "title": "Total MSW Generated per Year"
    }
  ]
},
"config": {}
};
  vegaEmbed("#Bar", spec1, {mode: "vega-lite"}).then(console.log).catch(console.warn);
</script>

<script>
  const spec4 = {
"$schema": "https://vega.github.io/schema/vega-lite/v5.json",
"width": 500,
"height": 300,
"title": "GDP Chloropeth Map",
"data": {
  "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/ne_110m_admin_0_countries.topojson",
  "format": {"type": "topojson", "feature": "ne_110m_admin_0_countries"}
},
"transform": [
  {
    "lookup": "properties.NAME",
    "from": {
      "data": {
        "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/country_level_data_0.csv"
      },
      "key": "country_name",
      "fields": ["gdp"]
    }
  }
],
"projection": {"type": "equirectangular"},
"mark": "geoshape",
"encoding": {
  "color": {
    "field": "gdp",
    "type": "quantitative",
    "scale": {
      "type": "linear",
      "domain": [10000, 100000],
      "scheme": "tealblues"
    },
    "condition": {
      "test": "datum['gdp'] === null || datum['country_name'] === null",
      "value": "#D9DDDC"
    }
  },
  "tooltip": [
    {"field": "gdp", "title": "GDP", "type": "quantitative", "format": ".2f"}
  ]
},
"config": {"mark": {"invalid": null}}
};
  vegaEmbed("#Map", spec4, {mode: "vega-lite"}).then(console.log).catch(console.warn);
</script>

<script>
  const spec = {
"$schema": "https://vega.github.io/schema/vega-lite/v2.json",
"title": "Waste Collection vs Total MSW",
"data": {
  "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/country_level_data_0.csv"
},
"mark": "circle",
"encoding": {
  "y": {
    "field": "total_msw_total_msw_generated_tons_year",
    "type": "quantitative",
    "title": "Total MSW (in tons) per Year",
    "scale": {"type": "linear", "domain": [0, 80000000]}
  },
  "x": {
    "field": "waste_collection_coverage_total_percent_of_waste",
    "type": "quantitative",
    "title": "Total Waste Collection",
    "scale": {"type": "linear", "domain": [0, 105]}
  },
  "tooltip": [
    {
      "field": "waste_collection_coverage_total_percent_of_waste",
      "type": "quantitative",
      "title": "Total Waste Collection (percentage)"
    },
    {
      "field": "total_msw_total_msw_generated_tons_year",
      "type": "quantitative",
      "aggregate": "sum",
      "title": "Total MSW Generated per Year"
    }
  ],
  "color": {
    "field": "waste_collection_coverage_total_percent_of_waste",
    "type": "quantitative",
    "title": "Total Waste Collection"
  }
},
"config": {}
};
  vegaEmbed("Scatter01", spec2, {mode: "vega-lite"}).then(console.log).catch(console.warn);
</script>

<script>
  const spec5 = {
"$schema": "https://vega.github.io/schema/vega/v5.json",
"width": 800,
"height": 600,
"title": "Population per Country",
"padding": {"left": 5, "right": 5, "top": 20, "bottom": 0},
"autosize": "none",
"signals": [
  {"name": "cx", "update": "width / 2"},
  {"name": "cy", "update": "height / 2"},
  {
    "name": "gravityX",
    "value": 0.2,
    "bind": {"input": "range", "min": 0, "max": 1}
  },
  {
    "name": "gravityY",
    "value": 0.1,
    "bind": {"input": "range", "min": 0, "max": 1}
  }
],
"data": [
  {
    "name": "Country",
    "url": "https://raw.githubusercontent.com/rruuzz/FathimaRuzaiqaMohamedNaushad-DV2/main/country_level_data_0.csv",
    "format": {"type": "csv", "delimiter": ","}
  }
],
"scales": [
  {
    "name": "size",
    "domain": {
      "data": "Country",
      "field": "population_population_number_of_people"
    },
    "range": [0, 35000]
  },
  {
    "name": "color",
    "type": "ordinal",
    "domain": {"data": "Country", "field": "country_name"},
    "range": {"scheme": "category20"}
  }
],
"marks": [
  {
    "name": "nodes",
    "type": "symbol",
    "from": {"data": "Country"},
    "encode": {
      "enter": {
        "fill": {"scale": "color", "field": "country_name"},
        "xfocus": {"signal": "cx"},
        "yfocus": {"signal": "cy"}
      },
      "update": {
        "size": {
          "signal": "datum.population_population_number_of_people",
          "scale": "size"
        },
        "stroke": {"value": "white"},
        "strokeWidth": {"value": 1},
        "tooltip": {
          "signal": "{'Country Name': datum.country_name, 'Population': datum.population_population_number_of_people}"
        }
      }
    },
    "transform": [
      {
        "type": "force",
        "iterations": 100,
        "static": false,
        "forces": [
          {
            "force": "collide",
            "iterations": 2,
            "radius": {"expr": "sqrt(datum.size) / 2"}
          },
          {"force": "center", "x": {"signal": "cx"}, "y": {"signal": "cy"}},
          {"force": "x", "x": "xfocus", "strength": {"signal": "gravityX"}},
          {"force": "y", "y": "yfocus", "strength": {"signal": "gravityY"}}
        ]
      }
    ]
  }
],
"config": {}
};
  vegaEmbed("#Bubble", spec5, {mode: "vega"}).then(console.log).catch(console.warn);
</script>

</body>
</html>
