---
title: NVD3 with rCharts
date: "2014-01-14"
config: "../config.yml"
hitheme: solarized_dark
description: >
 This is a short tutorial on using NVD3 with rCharts to create interactive visualizations.
--- &article2

.message This is a demo of using [NVD3](http://nvd3.org) with [rCharts](http://rcharts.io). It requires installation of rCharts >= 0.4.2.


Our first step is to load `rCharts` and set the appropriate options so that the charts are rendered as inline iframes. Note that you don't need these settings, if you are running the examples interactively in your R console.


```r
library(rCharts)
options(
  rcharts.mode = 'iframesrc', 
  rcharts.cdn = TRUE,
  RCHART_WIDTH = 600,
  RCHART_HEIGHT = 400
)
library(knitr)
opts_chunk$set(tidy = F, results = 'asis', comment = NA)
```


## Stacked Area Chart


```r
dat <- data.frame(
  t = rep(0:23, each = 4), 
  var = rep(LETTERS[1:4], 4), 
  val = round(runif(4*24,0,50))
)
p8 <- nPlot(val ~ t, group =  'var', data = dat, 
 type = 'stackedAreaChart', id = 'chart'
)
p8
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e353178e67f&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e353178e67f()
    });
    function drawchart5e353178e67f(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e353178e67f&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;t&quot;,
&quot;y&quot;: &quot;val&quot;,
&quot;group&quot;: &quot;var&quot;,
&quot;type&quot;: &quot;stackedAreaChart&quot;,
&quot;id&quot;: &quot;chart5e353178e67f&quot; 
},
        data = [
 {
 &quot;t&quot;: 0,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             36 
},
{
 &quot;t&quot;: 0,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 0,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             22 
},
{
 &quot;t&quot;: 0,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             45 
},
{
 &quot;t&quot;: 1,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:              6 
},
{
 &quot;t&quot;: 1,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             11 
},
{
 &quot;t&quot;: 1,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 1,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             20 
},
{
 &quot;t&quot;: 2,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             33 
},
{
 &quot;t&quot;: 2,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             11 
},
{
 &quot;t&quot;: 2,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 2,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             48 
},
{
 &quot;t&quot;: 3,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:              7 
},
{
 &quot;t&quot;: 3,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             49 
},
{
 &quot;t&quot;: 3,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:              5 
},
{
 &quot;t&quot;: 3,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             31 
},
{
 &quot;t&quot;: 4,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             30 
},
{
 &quot;t&quot;: 4,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             38 
},
{
 &quot;t&quot;: 4,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             31 
},
{
 &quot;t&quot;: 4,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             33 
},
{
 &quot;t&quot;: 5,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:              7 
},
{
 &quot;t&quot;: 5,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             34 
},
{
 &quot;t&quot;: 5,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 5,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 6,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             24 
},
{
 &quot;t&quot;: 6,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             17 
},
{
 &quot;t&quot;: 6,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             13 
},
{
 &quot;t&quot;: 6,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             26 
},
{
 &quot;t&quot;: 7,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:              5 
},
{
 &quot;t&quot;: 7,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              3 
},
{
 &quot;t&quot;: 7,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             16 
},
{
 &quot;t&quot;: 7,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             23 
},
{
 &quot;t&quot;: 8,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             33 
},
{
 &quot;t&quot;: 8,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             39 
},
{
 &quot;t&quot;: 8,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             49 
},
{
 &quot;t&quot;: 8,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:              3 
},
{
 &quot;t&quot;: 9,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             27 
},
{
 &quot;t&quot;: 9,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              3 
},
{
 &quot;t&quot;: 9,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             22 
},
{
 &quot;t&quot;: 9,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             24 
},
{
 &quot;t&quot;: 10,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             48 
},
{
 &quot;t&quot;: 10,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             21 
},
{
 &quot;t&quot;: 10,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             40 
},
{
 &quot;t&quot;: 10,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             39 
},
{
 &quot;t&quot;: 11,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             24 
},
{
 &quot;t&quot;: 11,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             41 
},
{
 &quot;t&quot;: 11,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             34 
},
{
 &quot;t&quot;: 11,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             41 
},
{
 &quot;t&quot;: 12,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             29 
},
{
 &quot;t&quot;: 12,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              9 
},
{
 &quot;t&quot;: 12,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             22 
},
{
 &quot;t&quot;: 12,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 13,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 13,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              5 
},
{
 &quot;t&quot;: 13,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:              1 
},
{
 &quot;t&quot;: 13,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             11 
},
{
 &quot;t&quot;: 14,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             48 
},
{
 &quot;t&quot;: 14,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             35 
},
{
 &quot;t&quot;: 14,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             36 
},
{
 &quot;t&quot;: 14,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             47 
},
{
 &quot;t&quot;: 15,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             18 
},
{
 &quot;t&quot;: 15,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              6 
},
{
 &quot;t&quot;: 15,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 15,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             26 
},
{
 &quot;t&quot;: 16,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             42 
},
{
 &quot;t&quot;: 16,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             47 
},
{
 &quot;t&quot;: 16,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             42 
},
{
 &quot;t&quot;: 16,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             38 
},
{
 &quot;t&quot;: 17,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:              5 
},
{
 &quot;t&quot;: 17,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             34 
},
{
 &quot;t&quot;: 17,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             44 
},
{
 &quot;t&quot;: 17,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             26 
},
{
 &quot;t&quot;: 18,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             10 
},
{
 &quot;t&quot;: 18,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:              9 
},
{
 &quot;t&quot;: 18,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             31 
},
{
 &quot;t&quot;: 18,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             43 
},
{
 &quot;t&quot;: 19,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 19,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             45 
},
{
 &quot;t&quot;: 19,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             18 
},
{
 &quot;t&quot;: 19,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             45 
},
{
 &quot;t&quot;: 20,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             18 
},
{
 &quot;t&quot;: 20,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             31 
},
{
 &quot;t&quot;: 20,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             42 
},
{
 &quot;t&quot;: 20,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             35 
},
{
 &quot;t&quot;: 21,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             28 
},
{
 &quot;t&quot;: 21,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             41 
},
{
 &quot;t&quot;: 21,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             24 
},
{
 &quot;t&quot;: 21,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             29 
},
{
 &quot;t&quot;: 22,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 22,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             25 
},
{
 &quot;t&quot;: 22,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 22,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             10 
},
{
 &quot;t&quot;: 23,
&quot;var&quot;: &quot;A&quot;,
&quot;val&quot;:             46 
},
{
 &quot;t&quot;: 23,
&quot;var&quot;: &quot;B&quot;,
&quot;val&quot;:             28 
},
{
 &quot;t&quot;: 23,
&quot;var&quot;: &quot;C&quot;,
&quot;val&quot;:             34 
},
{
 &quot;t&quot;: 23,
&quot;var&quot;: &quot;D&quot;,
&quot;val&quot;:             41 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e353178e67f'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


## Scatter Chart


```r
p1 <- nPlot(mpg ~ wt, group = 'cyl', data = mtcars, type = 'scatterChart')
p1$xAxis(axisLabel = 'Weight (in lb)')
p1
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e351bb5ad48&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e351bb5ad48()
    });
    function drawchart5e351bb5ad48(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e351bb5ad48&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;wt&quot;,
&quot;y&quot;: &quot;mpg&quot;,
&quot;group&quot;: &quot;cyl&quot;,
&quot;type&quot;: &quot;scatterChart&quot;,
&quot;id&quot;: &quot;chart5e351bb5ad48&quot; 
},
        data = [
 {
 &quot;mpg&quot;:             21,
&quot;cyl&quot;:              6,
&quot;disp&quot;:            160,
&quot;hp&quot;:            110,
&quot;drat&quot;:            3.9,
&quot;wt&quot;:           2.62,
&quot;qsec&quot;:          16.46,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:             21,
&quot;cyl&quot;:              6,
&quot;disp&quot;:            160,
&quot;hp&quot;:            110,
&quot;drat&quot;:            3.9,
&quot;wt&quot;:          2.875,
&quot;qsec&quot;:          17.02,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           22.8,
&quot;cyl&quot;:              4,
&quot;disp&quot;:            108,
&quot;hp&quot;:             93,
&quot;drat&quot;:           3.85,
&quot;wt&quot;:           2.32,
&quot;qsec&quot;:          18.61,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           21.4,
&quot;cyl&quot;:              6,
&quot;disp&quot;:            258,
&quot;hp&quot;:            110,
&quot;drat&quot;:           3.08,
&quot;wt&quot;:          3.215,
&quot;qsec&quot;:          19.44,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           18.7,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            360,
&quot;hp&quot;:            175,
&quot;drat&quot;:           3.15,
&quot;wt&quot;:           3.44,
&quot;qsec&quot;:          17.02,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           18.1,
&quot;cyl&quot;:              6,
&quot;disp&quot;:            225,
&quot;hp&quot;:            105,
&quot;drat&quot;:           2.76,
&quot;wt&quot;:           3.46,
&quot;qsec&quot;:          20.22,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           14.3,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            360,
&quot;hp&quot;:            245,
&quot;drat&quot;:           3.21,
&quot;wt&quot;:           3.57,
&quot;qsec&quot;:          15.84,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           24.4,
&quot;cyl&quot;:              4,
&quot;disp&quot;:          146.7,
&quot;hp&quot;:             62,
&quot;drat&quot;:           3.69,
&quot;wt&quot;:           3.19,
&quot;qsec&quot;:             20,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              4,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           22.8,
&quot;cyl&quot;:              4,
&quot;disp&quot;:          140.8,
&quot;hp&quot;:             95,
&quot;drat&quot;:           3.92,
&quot;wt&quot;:           3.15,
&quot;qsec&quot;:           22.9,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              4,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           19.2,
&quot;cyl&quot;:              6,
&quot;disp&quot;:          167.6,
&quot;hp&quot;:            123,
&quot;drat&quot;:           3.92,
&quot;wt&quot;:           3.44,
&quot;qsec&quot;:           18.3,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              4,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           17.8,
&quot;cyl&quot;:              6,
&quot;disp&quot;:          167.6,
&quot;hp&quot;:            123,
&quot;drat&quot;:           3.92,
&quot;wt&quot;:           3.44,
&quot;qsec&quot;:           18.9,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              4,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           16.4,
&quot;cyl&quot;:              8,
&quot;disp&quot;:          275.8,
&quot;hp&quot;:            180,
&quot;drat&quot;:           3.07,
&quot;wt&quot;:           4.07,
&quot;qsec&quot;:           17.4,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              3 
},
{
 &quot;mpg&quot;:           17.3,
&quot;cyl&quot;:              8,
&quot;disp&quot;:          275.8,
&quot;hp&quot;:            180,
&quot;drat&quot;:           3.07,
&quot;wt&quot;:           3.73,
&quot;qsec&quot;:           17.6,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              3 
},
{
 &quot;mpg&quot;:           15.2,
&quot;cyl&quot;:              8,
&quot;disp&quot;:          275.8,
&quot;hp&quot;:            180,
&quot;drat&quot;:           3.07,
&quot;wt&quot;:           3.78,
&quot;qsec&quot;:             18,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              3 
},
{
 &quot;mpg&quot;:           10.4,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            472,
&quot;hp&quot;:            205,
&quot;drat&quot;:           2.93,
&quot;wt&quot;:           5.25,
&quot;qsec&quot;:          17.98,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           10.4,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            460,
&quot;hp&quot;:            215,
&quot;drat&quot;:              3,
&quot;wt&quot;:          5.424,
&quot;qsec&quot;:          17.82,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           14.7,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            440,
&quot;hp&quot;:            230,
&quot;drat&quot;:           3.23,
&quot;wt&quot;:          5.345,
&quot;qsec&quot;:          17.42,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           32.4,
&quot;cyl&quot;:              4,
&quot;disp&quot;:           78.7,
&quot;hp&quot;:             66,
&quot;drat&quot;:           4.08,
&quot;wt&quot;:            2.2,
&quot;qsec&quot;:          19.47,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           30.4,
&quot;cyl&quot;:              4,
&quot;disp&quot;:           75.7,
&quot;hp&quot;:             52,
&quot;drat&quot;:           4.93,
&quot;wt&quot;:          1.615,
&quot;qsec&quot;:          18.52,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           33.9,
&quot;cyl&quot;:              4,
&quot;disp&quot;:           71.1,
&quot;hp&quot;:             65,
&quot;drat&quot;:           4.22,
&quot;wt&quot;:          1.835,
&quot;qsec&quot;:           19.9,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           21.5,
&quot;cyl&quot;:              4,
&quot;disp&quot;:          120.1,
&quot;hp&quot;:             97,
&quot;drat&quot;:            3.7,
&quot;wt&quot;:          2.465,
&quot;qsec&quot;:          20.01,
&quot;vs&quot;:              1,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:           15.5,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            318,
&quot;hp&quot;:            150,
&quot;drat&quot;:           2.76,
&quot;wt&quot;:           3.52,
&quot;qsec&quot;:          16.87,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           15.2,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            304,
&quot;hp&quot;:            150,
&quot;drat&quot;:           3.15,
&quot;wt&quot;:          3.435,
&quot;qsec&quot;:           17.3,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           13.3,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            350,
&quot;hp&quot;:            245,
&quot;drat&quot;:           3.73,
&quot;wt&quot;:           3.84,
&quot;qsec&quot;:          15.41,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           19.2,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            400,
&quot;hp&quot;:            175,
&quot;drat&quot;:           3.08,
&quot;wt&quot;:          3.845,
&quot;qsec&quot;:          17.05,
&quot;vs&quot;:              0,
&quot;am&quot;:              0,
&quot;gear&quot;:              3,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           27.3,
&quot;cyl&quot;:              4,
&quot;disp&quot;:             79,
&quot;hp&quot;:             66,
&quot;drat&quot;:           4.08,
&quot;wt&quot;:          1.935,
&quot;qsec&quot;:           18.9,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              1 
},
{
 &quot;mpg&quot;:             26,
&quot;cyl&quot;:              4,
&quot;disp&quot;:          120.3,
&quot;hp&quot;:             91,
&quot;drat&quot;:           4.43,
&quot;wt&quot;:           2.14,
&quot;qsec&quot;:           16.7,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              5,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           30.4,
&quot;cyl&quot;:              4,
&quot;disp&quot;:           95.1,
&quot;hp&quot;:            113,
&quot;drat&quot;:           3.77,
&quot;wt&quot;:          1.513,
&quot;qsec&quot;:           16.9,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              5,
&quot;carb&quot;:              2 
},
{
 &quot;mpg&quot;:           15.8,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            351,
&quot;hp&quot;:            264,
&quot;drat&quot;:           4.22,
&quot;wt&quot;:           3.17,
&quot;qsec&quot;:           14.5,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              5,
&quot;carb&quot;:              4 
},
{
 &quot;mpg&quot;:           19.7,
&quot;cyl&quot;:              6,
&quot;disp&quot;:            145,
&quot;hp&quot;:            175,
&quot;drat&quot;:           3.62,
&quot;wt&quot;:           2.77,
&quot;qsec&quot;:           15.5,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              5,
&quot;carb&quot;:              6 
},
{
 &quot;mpg&quot;:             15,
&quot;cyl&quot;:              8,
&quot;disp&quot;:            301,
&quot;hp&quot;:            335,
&quot;drat&quot;:           3.54,
&quot;wt&quot;:           3.57,
&quot;qsec&quot;:           14.6,
&quot;vs&quot;:              0,
&quot;am&quot;:              1,
&quot;gear&quot;:              5,
&quot;carb&quot;:              8 
},
{
 &quot;mpg&quot;:           21.4,
&quot;cyl&quot;:              4,
&quot;disp&quot;:            121,
&quot;hp&quot;:            109,
&quot;drat&quot;:           4.11,
&quot;wt&quot;:           2.78,
&quot;qsec&quot;:           18.6,
&quot;vs&quot;:              1,
&quot;am&quot;:              1,
&quot;gear&quot;:              4,
&quot;carb&quot;:              2 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        chart.xAxis
  .axisLabel(&quot;Weight (in lb)&quot;)

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e351bb5ad48'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>



## Multibar Chart


```r
hair_eye = as.data.frame(HairEyeColor)
p2 <- nPlot(Freq ~ Hair, group = 'Eye', 
  data = subset(hair_eye, Sex == "Female"), 
  type = 'multiBarChart'
)
p2$chart(color = c('brown', 'blue', '#594c26', 'green'))
p2
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart67ca2b52979d&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart67ca2b52979d()
    });
    function drawchart67ca2b52979d(){  
      var opts = {
 &quot;dom&quot;: &quot;chart67ca2b52979d&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;Hair&quot;,
&quot;y&quot;: &quot;Freq&quot;,
&quot;group&quot;: &quot;Eye&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart67ca2b52979d&quot; 
},
        data = [
 {
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             36 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             66 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             16 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              4 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              9 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             34 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             64 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              5 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             29 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              5 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              2 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             14 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              8 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .color([ &quot;brown&quot;, &quot;blue&quot;, &quot;#594c26&quot;, &quot;green&quot; ])
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart67ca2b52979d'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


## Multibar Chart with Controls


```r
hair_eye = as.data.frame(HairEyeColor)
p2a <- nPlot(Freq ~ Hair, group = 'Eye', 
  data = hair_eye,
  type = 'multiBarChart'
)
p2a$chart(color = c('brown', 'blue', '#594c26', 'green'))
p2a$addFilters("Sex")
p2a$set(dom = 'chart2', width = 600)
p2a
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&quot;http://netdna.bootstrapcdn.com/bootstrap/3.0.3/css/bootstrap.min.css&quot;&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
     &lt;script src=&quot;http://ajax.googleapis.com/ajax/libs/angularjs/1.2.6/angular.min.js&quot;&gt;&lt;/script&gt;
     &lt;script src=&quot;http://cdnjs.cloudflare.com/ajax/libs/lodash.js/2.4.1/lodash.min.js&quot;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block
      margin: auto auto;
      width: 100%;
      height: 400px;
    }
    .bs-docs-example:after {
      content: &quot;&quot;;
      background: transparent;
      border: none;
    }
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body ng-app&gt;
      
    &lt;div class=&#039;container&#039; ng-controller=&quot;DemoCtrl&quot;&gt;
  &lt;div class=&#039;row&#039;&gt;
    &lt;div class=&#039;col-md-3&#039;&gt;
      &lt;form class=&#039;well&#039;&gt;
        
        &lt;select
          ng-model=&quot;selected&quot; 
          ng-options=&quot;c as c.value group by c.variable for c in filters&quot; 
          class=&quot;form-control&quot; multiple size=&quot;10&quot;&gt;
        &lt;/select&gt;
      &lt;/form&gt;
    &lt;/div&gt;
    &lt;div class=&#039;col-md-8&#039;&gt;
      &lt;div class=&quot;bs-docs-example&quot;&gt;
        &lt;div id=&#039;chart2&#039; class=&#039;rChart &#039;&gt;
          &lt;svg&gt;&lt;/svg&gt;
        &lt;/div&gt;
        
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;script type=&quot;text/javascript&quot;&gt;
function DemoCtrl($scope){
  $scope.opts = {
 &quot;dom&quot;: &quot;chart2&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;Hair&quot;,
&quot;y&quot;: &quot;Freq&quot;,
&quot;group&quot;: &quot;Eye&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart2&quot; 
}
  $scope.data = [
 {
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             32 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             53 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             10 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              3 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             11 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             50 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             10 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             30 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             10 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             25 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              5 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              3 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:             15 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Male&quot;,
&quot;Freq&quot;:              8 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             36 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             66 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             16 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Brown&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              4 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              9 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             34 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Blue&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             64 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              5 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             29 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Hazel&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              5 
},
{
 &quot;Hair&quot;: &quot;Black&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              2 
},
{
 &quot;Hair&quot;: &quot;Brown&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:             14 
},
{
 &quot;Hair&quot;: &quot;Red&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              7 
},
{
 &quot;Hair&quot;: &quot;Blond&quot;,
&quot;Eye&quot;: &quot;Green&quot;,
&quot;Sex&quot;: &quot;Female&quot;,
&quot;Freq&quot;:              8 
} 
]
  $scope.controls = [] 
  $scope.filters = [
 {
 &quot;variable&quot;: &quot;Sex&quot;,
&quot;value&quot;: &quot;Male&quot; 
},
{
 &quot;variable&quot;: &quot;Sex&quot;,
&quot;value&quot;: &quot;Female&quot; 
} 
]
  
  $scope.drawChart = function(){
    drawChart($scope.opts, $scope.data)  
  }
  
  $scope.$watch(&#039;selected&#039;, function(){
    var keys = _.pluck($scope.selected, &quot;variable&quot;)
    var values = _.pluck($scope.selected, &quot;value&quot;)
    $scope.opts.selected = _.zipObject(keys, values)
  }) 
  
  $scope.$watch(&#039;opts&#039;,function(){
    $scope.drawChart()
	}, true)
}  

function drawChart(opts, data){ 
  if (Object.keys(opts.selected).length &gt; 0){
    data = _.filter(data, opts.selected)
  }
  
  if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
    var data = d3.nest()
      .key(function(d){
        //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
        //instead of main would think a better default is opts.x
       return opts.group === undefined ? opts.y : d[opts.group];
      }).entries(data);
  }
      
  if (opts.disabled != undefined){
    data.map(function(d, i){
      d.disabled = opts.disabled[i]
    })
  }
	
	nv.addGraph(function() {
		var chart = nv.models[opts.type]()
			.x(function(d) { return d[opts.x] })
			.y(function(d) { return d[opts.y] })
			.width(opts.width)
			.height(opts.height)
		
	chart
  .color([ &quot;brown&quot;, &quot;blue&quot;, &quot;#594c26&quot;, &quot;green&quot; ])
          
	

	
	
	

	d3.select(&quot;#&quot; + opts.id + &#039; svg&#039;)
  // .empty()
		.datum(data)
		.transition().duration(500)
		.call(chart);
	
	 nv.utils.windowResize(chart.update);
	 return chart;
  });
};
&lt;/script&gt;
    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart2'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


<style>#iframe-chart2{height: 700px;}</style>


## Multibar Horizontal Chart


```r
p3 <- nPlot(~ cyl, group = 'gear', data = mtcars, type = 'multiBarHorizontalChart')
p3$chart(showControls = F)
p3
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e35513fea08&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e35513fea08()
    });
    function drawchart5e35513fea08(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e35513fea08&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;cyl&quot;,
&quot;y&quot;: &quot;freq&quot;,
&quot;group&quot;: &quot;gear&quot;,
&quot;type&quot;: &quot;multiBarHorizontalChart&quot;,
&quot;id&quot;: &quot;chart5e35513fea08&quot; 
},
        data = [
 {
 &quot;cyl&quot;:              4,
&quot;gear&quot;:              3,
&quot;freq&quot;: 1 
},
{
 &quot;cyl&quot;:              4,
&quot;gear&quot;:              4,
&quot;freq&quot;: 8 
},
{
 &quot;cyl&quot;:              4,
&quot;gear&quot;:              5,
&quot;freq&quot;: 2 
},
{
 &quot;cyl&quot;:              6,
&quot;gear&quot;:              3,
&quot;freq&quot;: 2 
},
{
 &quot;cyl&quot;:              6,
&quot;gear&quot;:              4,
&quot;freq&quot;: 4 
},
{
 &quot;cyl&quot;:              6,
&quot;gear&quot;:              5,
&quot;freq&quot;: 1 
},
{
 &quot;cyl&quot;:              8,
&quot;gear&quot;:              3,
&quot;freq&quot;: 12 
},
{
 &quot;cyl&quot;:              8,
&quot;gear&quot;:              5,
&quot;freq&quot;: 2 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .showControls(false)
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e35513fea08'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


## Pie Chart


```r
p4 <- nPlot(~ cyl, data = mtcars, type = 'pieChart')
p4
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e3525911b0e&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e3525911b0e()
    });
    function drawchart5e3525911b0e(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e3525911b0e&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;cyl&quot;,
&quot;y&quot;: &quot;freq&quot;,
&quot;type&quot;: &quot;pieChart&quot;,
&quot;id&quot;: &quot;chart5e3525911b0e&quot; 
},
        data = [
 {
 &quot;cyl&quot;:              4,
&quot;freq&quot;: 11 
},
{
 &quot;cyl&quot;:              6,
&quot;freq&quot;: 7 
},
{
 &quot;cyl&quot;:              8,
&quot;freq&quot;: 14 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e3525911b0e'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


## Donut Chart


```r
p5 <- nPlot(~ cyl, data = mtcars, type = 'pieChart')
p5$chart(donut = TRUE)
p5
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e354060a775&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e354060a775()
    });
    function drawchart5e354060a775(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e354060a775&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;cyl&quot;,
&quot;y&quot;: &quot;freq&quot;,
&quot;type&quot;: &quot;pieChart&quot;,
&quot;id&quot;: &quot;chart5e354060a775&quot; 
},
        data = [
 {
 &quot;cyl&quot;:              4,
&quot;freq&quot;: 11 
},
{
 &quot;cyl&quot;:              6,
&quot;freq&quot;: 7 
},
{
 &quot;cyl&quot;:              8,
&quot;freq&quot;: 14 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .donut(true)
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e354060a775'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>


## Line Chart


```r
data(economics, package = 'ggplot2')
p6 <- nPlot(uempmed ~ date, data = economics, type = 'lineChart')
p6
```

<iframe srcdoc='
&lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;http://nvd3.org/assets/css/nv.d3.css&#039;&gt;
    
    &lt;script src=&#039;http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://timelyportfolio.github.io/rCharts_nvd3_tests/libraries/widgets/nvd3/js/nv.d3.min-new.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;http://nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 600px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart5e355533fb50&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart5e355533fb50()
    });
    function drawchart5e355533fb50(){  
      var opts = {
 &quot;dom&quot;: &quot;chart5e355533fb50&quot;,
&quot;width&quot;:    600,
&quot;height&quot;:    400,
&quot;process_data&quot;: true,
&quot;x&quot;: &quot;date&quot;,
&quot;y&quot;: &quot;uempmed&quot;,
&quot;type&quot;: &quot;lineChart&quot;,
&quot;id&quot;: &quot;chart5e355533fb50&quot; 
},
        data = [
 {
 &quot;date&quot;:           -916,
&quot;pce&quot;:          507.8,
&quot;pop&quot;: 198712,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            4.5,
&quot;unemploy&quot;: 2944 
},
{
 &quot;date&quot;:           -885,
&quot;pce&quot;:          510.9,
&quot;pop&quot;: 198911,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            4.7,
&quot;unemploy&quot;: 2945 
},
{
 &quot;date&quot;:           -854,
&quot;pce&quot;:          516.7,
&quot;pop&quot;: 199113,
&quot;psavert&quot;:              9,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 2958 
},
{
 &quot;date&quot;:           -824,
&quot;pce&quot;:          513.3,
&quot;pop&quot;: 199311,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 3143 
},
{
 &quot;date&quot;:           -793,
&quot;pce&quot;:          518.5,
&quot;pop&quot;: 199498,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            4.7,
&quot;unemploy&quot;: 3066 
},
{
 &quot;date&quot;:           -763,
&quot;pce&quot;:          526.2,
&quot;pop&quot;: 199657,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 3018 
},
{
 &quot;date&quot;:           -732,
&quot;pce&quot;:            532,
&quot;pop&quot;: 199808,
&quot;psavert&quot;:              9,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 2878 
},
{
 &quot;date&quot;:           -701,
&quot;pce&quot;:          534.7,
&quot;pop&quot;: 199920,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            4.5,
&quot;unemploy&quot;: 3001 
},
{
 &quot;date&quot;:           -672,
&quot;pce&quot;:          545.4,
&quot;pop&quot;: 200056,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            4.1,
&quot;unemploy&quot;: 2877 
},
{
 &quot;date&quot;:           -641,
&quot;pce&quot;:          545.1,
&quot;pop&quot;: 200208,
&quot;psavert&quot;:            9.6,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 2709 
},
{
 &quot;date&quot;:           -611,
&quot;pce&quot;:          550.9,
&quot;pop&quot;: 200361,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2740 
},
{
 &quot;date&quot;:           -580,
&quot;pce&quot;:          557.4,
&quot;pop&quot;: 200536,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2938 
},
{
 &quot;date&quot;:           -550,
&quot;pce&quot;:          564.4,
&quot;pop&quot;: 200706,
&quot;psavert&quot;:            7.8,
&quot;uempmed&quot;:            4.5,
&quot;unemploy&quot;: 2883 
},
{
 &quot;date&quot;:           -519,
&quot;pce&quot;:          568.2,
&quot;pop&quot;: 200898,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            4.2,
&quot;unemploy&quot;: 2768 
},
{
 &quot;date&quot;:           -488,
&quot;pce&quot;:          569.5,
&quot;pop&quot;: 201095,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 2686 
},
{
 &quot;date&quot;:           -458,
&quot;pce&quot;:          572.9,
&quot;pop&quot;: 201290,
&quot;psavert&quot;:            7.8,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 2689 
},
{
 &quot;date&quot;:           -427,
&quot;pce&quot;:            578,
&quot;pop&quot;: 201466,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2715 
},
{
 &quot;date&quot;:           -397,
&quot;pce&quot;:          577.9,
&quot;pop&quot;: 201621,
&quot;psavert&quot;:            8.1,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2685 
},
{
 &quot;date&quot;:           -366,
&quot;pce&quot;:          584.9,
&quot;pop&quot;: 201760,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2718 
},
{
 &quot;date&quot;:           -335,
&quot;pce&quot;:          590.2,
&quot;pop&quot;: 201881,
&quot;psavert&quot;:            6.5,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 2692 
},
{
 &quot;date&quot;:           -307,
&quot;pce&quot;:          590.4,
&quot;pop&quot;: 202023,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:              4,
&quot;unemploy&quot;: 2712 
},
{
 &quot;date&quot;:           -276,
&quot;pce&quot;:          595.4,
&quot;pop&quot;: 202161,
&quot;psavert&quot;:            6.6,
&quot;uempmed&quot;:              4,
&quot;unemploy&quot;: 2758 
},
{
 &quot;date&quot;:           -246,
&quot;pce&quot;:          601.8,
&quot;pop&quot;: 202331,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            4.2,
&quot;unemploy&quot;: 2713 
},
{
 &quot;date&quot;:           -215,
&quot;pce&quot;:          602.4,
&quot;pop&quot;: 202507,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2816 
},
{
 &quot;date&quot;:           -185,
&quot;pce&quot;:          604.3,
&quot;pop&quot;: 202677,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2868 
},
{
 &quot;date&quot;:           -154,
&quot;pce&quot;:          611.5,
&quot;pop&quot;: 202877,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            4.4,
&quot;unemploy&quot;: 2856 
},
{
 &quot;date&quot;:           -123,
&quot;pce&quot;:          614.9,
&quot;pop&quot;: 203090,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            4.7,
&quot;unemploy&quot;: 3040 
},
{
 &quot;date&quot;:            -93,
&quot;pce&quot;:          620.2,
&quot;pop&quot;: 203302,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            4.5,
&quot;unemploy&quot;: 3049 
},
{
 &quot;date&quot;:            -62,
&quot;pce&quot;:          622.1,
&quot;pop&quot;: 203500,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 2856 
},
{
 &quot;date&quot;:            -32,
&quot;pce&quot;:          624.4,
&quot;pop&quot;: 203675,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 2884 
},
{
 &quot;date&quot;:             -1,
&quot;pce&quot;:          630.4,
&quot;pop&quot;: 203849,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 3201 
},
{
 &quot;date&quot;:             30,
&quot;pce&quot;:          635.7,
&quot;pop&quot;: 204008,
&quot;psavert&quot;:            8.1,
&quot;uempmed&quot;:            4.5,
&quot;unemploy&quot;: 3453 
},
{
 &quot;date&quot;:             58,
&quot;pce&quot;:            634,
&quot;pop&quot;: 204156,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 3635 
},
{
 &quot;date&quot;:             89,
&quot;pce&quot;:          637.7,
&quot;pop&quot;: 204401,
&quot;psavert&quot;:           10.5,
&quot;uempmed&quot;:            4.1,
&quot;unemploy&quot;: 3797 
},
{
 &quot;date&quot;:            119,
&quot;pce&quot;:          644.1,
&quot;pop&quot;: 204607,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            4.7,
&quot;unemploy&quot;: 3919 
},
{
 &quot;date&quot;:            150,
&quot;pce&quot;:            648,
&quot;pop&quot;: 204830,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 4071 
},
{
 &quot;date&quot;:            180,
&quot;pce&quot;:          650.2,
&quot;pop&quot;: 205052,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 4175 
},
{
 &quot;date&quot;:            211,
&quot;pce&quot;:          654.7,
&quot;pop&quot;: 205295,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 4256 
},
{
 &quot;date&quot;:            242,
&quot;pce&quot;:          660.9,
&quot;pop&quot;: 205540,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 4456 
},
{
 &quot;date&quot;:            272,
&quot;pce&quot;:          660.1,
&quot;pop&quot;: 205788,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 4591 
},
{
 &quot;date&quot;:            303,
&quot;pce&quot;:          658.4,
&quot;pop&quot;: 206024,
&quot;psavert&quot;:           10.1,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 4898 
},
{
 &quot;date&quot;:            333,
&quot;pce&quot;:          667.4,
&quot;pop&quot;: 206238,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 5076 
},
{
 &quot;date&quot;:            364,
&quot;pce&quot;:            678,
&quot;pop&quot;: 206466,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 4986 
},
{
 &quot;date&quot;:            395,
&quot;pce&quot;:          681.3,
&quot;pop&quot;: 206668,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 4903 
},
{
 &quot;date&quot;:            423,
&quot;pce&quot;:          683.9,
&quot;pop&quot;: 206855,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 4987 
},
{
 &quot;date&quot;:            454,
&quot;pce&quot;:          690.6,
&quot;pop&quot;: 207065,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 4959 
},
{
 &quot;date&quot;:            484,
&quot;pce&quot;:            693,
&quot;pop&quot;: 207260,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 4996 
},
{
 &quot;date&quot;:            515,
&quot;pce&quot;:          701.7,
&quot;pop&quot;: 207462,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 4949 
},
{
 &quot;date&quot;:            545,
&quot;pce&quot;:          700.8,
&quot;pop&quot;: 207661,
&quot;psavert&quot;:           10.4,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 5035 
},
{
 &quot;date&quot;:            576,
&quot;pce&quot;:          706.8,
&quot;pop&quot;: 207881,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 5134 
},
{
 &quot;date&quot;:            607,
&quot;pce&quot;:            715,
&quot;pop&quot;: 208114,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 5042 
},
{
 &quot;date&quot;:            637,
&quot;pce&quot;:          717.8,
&quot;pop&quot;: 208345,
&quot;psavert&quot;:            9.6,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 4954 
},
{
 &quot;date&quot;:            668,
&quot;pce&quot;:            723,
&quot;pop&quot;: 208555,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 5161 
},
{
 &quot;date&quot;:            698,
&quot;pce&quot;:          730.5,
&quot;pop&quot;: 208740,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 5154 
},
{
 &quot;date&quot;:            729,
&quot;pce&quot;:          733.7,
&quot;pop&quot;: 208917,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 5019 
},
{
 &quot;date&quot;:            760,
&quot;pce&quot;:          738.4,
&quot;pop&quot;: 209061,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 4928 
},
{
 &quot;date&quot;:            789,
&quot;pce&quot;:          751.5,
&quot;pop&quot;: 209212,
&quot;psavert&quot;:            8.2,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 5038 
},
{
 &quot;date&quot;:            820,
&quot;pce&quot;:          754.9,
&quot;pop&quot;: 209386,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 4959 
},
{
 &quot;date&quot;:            850,
&quot;pce&quot;:          760.4,
&quot;pop&quot;: 209545,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 4922 
},
{
 &quot;date&quot;:            881,
&quot;pce&quot;:            764,
&quot;pop&quot;: 209725,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 4923 
},
{
 &quot;date&quot;:            911,
&quot;pce&quot;:          772.4,
&quot;pop&quot;: 209896,
&quot;psavert&quot;:            8.2,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 4913 
},
{
 &quot;date&quot;:            942,
&quot;pce&quot;:          778.9,
&quot;pop&quot;: 210075,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 4939 
},
{
 &quot;date&quot;:            973,
&quot;pce&quot;:          783.7,
&quot;pop&quot;: 210278,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 4849 
},
{
 &quot;date&quot;:           1003,
&quot;pce&quot;:          797.5,
&quot;pop&quot;: 210479,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 4875 
},
{
 &quot;date&quot;:           1034,
&quot;pce&quot;:          803.1,
&quot;pop&quot;: 210656,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 4602 
},
{
 &quot;date&quot;:           1064,
&quot;pce&quot;:          808.8,
&quot;pop&quot;: 210821,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 4543 
},
{
 &quot;date&quot;:           1095,
&quot;pce&quot;:          819.1,
&quot;pop&quot;: 210985,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 4326 
},
{
 &quot;date&quot;:           1126,
&quot;pce&quot;:          828.5,
&quot;pop&quot;: 211120,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 4452 
},
{
 &quot;date&quot;:           1154,
&quot;pce&quot;:          835.5,
&quot;pop&quot;: 211254,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 4394 
},
{
 &quot;date&quot;:           1185,
&quot;pce&quot;:          838.5,
&quot;pop&quot;: 211420,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 4459 
},
{
 &quot;date&quot;:           1215,
&quot;pce&quot;:          844.3,
&quot;pop&quot;: 211577,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 4329 
},
{
 &quot;date&quot;:           1246,
&quot;pce&quot;:          847.1,
&quot;pop&quot;: 211746,
&quot;psavert&quot;:           10.7,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 4363 
},
{
 &quot;date&quot;:           1276,
&quot;pce&quot;:            857,
&quot;pop&quot;: 211909,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 4305 
},
{
 &quot;date&quot;:           1307,
&quot;pce&quot;:          856.1,
&quot;pop&quot;: 212092,
&quot;psavert&quot;:             11,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 4305 
},
{
 &quot;date&quot;:           1338,
&quot;pce&quot;:          872.2,
&quot;pop&quot;: 212289,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 4350 
},
{
 &quot;date&quot;:           1368,
&quot;pce&quot;:          871.2,
&quot;pop&quot;: 212475,
&quot;psavert&quot;:           11.5,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 4144 
},
{
 &quot;date&quot;:           1399,
&quot;pce&quot;:          879.9,
&quot;pop&quot;: 212634,
&quot;psavert&quot;:           11.6,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 4396 
},
{
 &quot;date&quot;:           1429,
&quot;pce&quot;:          879.7,
&quot;pop&quot;: 212785,
&quot;psavert&quot;:             12,
&quot;uempmed&quot;:            4.7,
&quot;unemploy&quot;: 4489 
},
{
 &quot;date&quot;:           1460,
&quot;pce&quot;:          887.7,
&quot;pop&quot;: 212932,
&quot;psavert&quot;:           11.6,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 4644 
},
{
 &quot;date&quot;:           1491,
&quot;pce&quot;:          892.9,
&quot;pop&quot;: 213074,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 4731 
},
{
 &quot;date&quot;:           1519,
&quot;pce&quot;:          904.7,
&quot;pop&quot;: 213211,
&quot;psavert&quot;:           10.6,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 4634 
},
{
 &quot;date&quot;:           1550,
&quot;pce&quot;:          914.1,
&quot;pop&quot;: 213361,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 4618 
},
{
 &quot;date&quot;:           1580,
&quot;pce&quot;:          925.7,
&quot;pop&quot;: 213513,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            4.6,
&quot;unemploy&quot;: 4705 
},
{
 &quot;date&quot;:           1611,
&quot;pce&quot;:          931.3,
&quot;pop&quot;: 213686,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 4927 
},
{
 &quot;date&quot;:           1641,
&quot;pce&quot;:          941.2,
&quot;pop&quot;: 213854,
&quot;psavert&quot;:           10.6,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 5063 
},
{
 &quot;date&quot;:           1672,
&quot;pce&quot;:            958,
&quot;pop&quot;: 214042,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 5022 
},
{
 &quot;date&quot;:           1703,
&quot;pce&quot;:          958.3,
&quot;pop&quot;: 214246,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 5437 
},
{
 &quot;date&quot;:           1733,
&quot;pce&quot;:          962.5,
&quot;pop&quot;: 214451,
&quot;psavert&quot;:           10.7,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 5523 
},
{
 &quot;date&quot;:           1764,
&quot;pce&quot;:          959.5,
&quot;pop&quot;: 214625,
&quot;psavert&quot;:           11.1,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 6140 
},
{
 &quot;date&quot;:           1794,
&quot;pce&quot;:          965.1,
&quot;pop&quot;: 214782,
&quot;psavert&quot;:           11.1,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 6636 
},
{
 &quot;date&quot;:           1825,
&quot;pce&quot;:          978.9,
&quot;pop&quot;: 214931,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 7501 
},
{
 &quot;date&quot;:           1856,
&quot;pce&quot;:          992.8,
&quot;pop&quot;: 215065,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 7520 
},
{
 &quot;date&quot;:           1884,
&quot;pce&quot;:          994.1,
&quot;pop&quot;: 215198,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 7978 
},
{
 &quot;date&quot;:           1915,
&quot;pce&quot;:          998.8,
&quot;pop&quot;: 215353,
&quot;psavert&quot;:           11.3,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 8210 
},
{
 &quot;date&quot;:           1945,
&quot;pce&quot;:         1022.8,
&quot;pop&quot;: 215523,
&quot;psavert&quot;:           14.6,
&quot;uempmed&quot;:            9.4,
&quot;unemploy&quot;: 8433 
},
{
 &quot;date&quot;:           1976,
&quot;pce&quot;:         1030.7,
&quot;pop&quot;: 215768,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            8.8,
&quot;unemploy&quot;: 8220 
},
{
 &quot;date&quot;:           2006,
&quot;pce&quot;:         1043.8,
&quot;pop&quot;: 215973,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 8127 
},
{
 &quot;date&quot;:           2037,
&quot;pce&quot;:           1051,
&quot;pop&quot;: 216195,
&quot;psavert&quot;:           10.1,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7928 
},
{
 &quot;date&quot;:           2068,
&quot;pce&quot;:         1058.9,
&quot;pop&quot;: 216393,
&quot;psavert&quot;:           10.2,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7923 
},
{
 &quot;date&quot;:           2098,
&quot;pce&quot;:         1064.8,
&quot;pop&quot;: 216587,
&quot;psavert&quot;:           10.7,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 7897 
},
{
 &quot;date&quot;:           2129,
&quot;pce&quot;:         1079.7,
&quot;pop&quot;: 216771,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 7794 
},
{
 &quot;date&quot;:           2159,
&quot;pce&quot;:           1096,
&quot;pop&quot;: 216931,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7744 
},
{
 &quot;date&quot;:           2190,
&quot;pce&quot;:         1111.2,
&quot;pop&quot;: 217095,
&quot;psavert&quot;:            9.2,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7534 
},
{
 &quot;date&quot;:           2221,
&quot;pce&quot;:         1111.8,
&quot;pop&quot;: 217249,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 7326 
},
{
 &quot;date&quot;:           2250,
&quot;pce&quot;:           1119,
&quot;pop&quot;: 217381,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 7230 
},
{
 &quot;date&quot;:           2281,
&quot;pce&quot;:         1129.6,
&quot;pop&quot;: 217528,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 7330 
},
{
 &quot;date&quot;:           2311,
&quot;pce&quot;:         1126.8,
&quot;pop&quot;: 217685,
&quot;psavert&quot;:           10.1,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7053 
},
{
 &quot;date&quot;:           2342,
&quot;pce&quot;:         1144.7,
&quot;pop&quot;: 217861,
&quot;psavert&quot;:            9.2,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 7322 
},
{
 &quot;date&quot;:           2372,
&quot;pce&quot;:         1153.8,
&quot;pop&quot;: 218035,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 7490 
},
{
 &quot;date&quot;:           2403,
&quot;pce&quot;:         1162.3,
&quot;pop&quot;: 218233,
&quot;psavert&quot;:            9.6,
&quot;uempmed&quot;:            7.9,
&quot;unemploy&quot;: 7518 
},
{
 &quot;date&quot;:           2434,
&quot;pce&quot;:         1173.2,
&quot;pop&quot;: 218440,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 7380 
},
{
 &quot;date&quot;:           2464,
&quot;pce&quot;:         1181.2,
&quot;pop&quot;: 218644,
&quot;psavert&quot;:              9,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 7430 
},
{
 &quot;date&quot;:           2495,
&quot;pce&quot;:         1193.5,
&quot;pop&quot;: 218834,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 7620 
},
{
 &quot;date&quot;:           2525,
&quot;pce&quot;:           1216,
&quot;pop&quot;: 219006,
&quot;psavert&quot;:            8.4,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 7545 
},
{
 &quot;date&quot;:           2556,
&quot;pce&quot;:         1219.3,
&quot;pop&quot;: 219179,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 7280 
},
{
 &quot;date&quot;:           2587,
&quot;pce&quot;:         1235.6,
&quot;pop&quot;: 219344,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 7443 
},
{
 &quot;date&quot;:           2615,
&quot;pce&quot;:         1242.6,
&quot;pop&quot;: 219504,
&quot;psavert&quot;:            8.4,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 7307 
},
{
 &quot;date&quot;:           2646,
&quot;pce&quot;:         1251.6,
&quot;pop&quot;: 219684,
&quot;psavert&quot;:            8.4,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 7059 
},
{
 &quot;date&quot;:           2676,
&quot;pce&quot;:         1261.5,
&quot;pop&quot;: 219859,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            7.9,
&quot;unemploy&quot;: 6911 
},
{
 &quot;date&quot;:           2707,
&quot;pce&quot;:         1268.2,
&quot;pop&quot;: 220046,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 7134 
},
{
 &quot;date&quot;:           2737,
&quot;pce&quot;:         1285.2,
&quot;pop&quot;: 220239,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 6829 
},
{
 &quot;date&quot;:           2768,
&quot;pce&quot;:         1290.4,
&quot;pop&quot;: 220458,
&quot;psavert&quot;:              9,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 6925 
},
{
 &quot;date&quot;:           2799,
&quot;pce&quot;:         1299.4,
&quot;pop&quot;: 220688,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 6751 
},
{
 &quot;date&quot;:           2829,
&quot;pce&quot;:         1316.3,
&quot;pop&quot;: 220904,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 6763 
},
{
 &quot;date&quot;:           2860,
&quot;pce&quot;:           1332,
&quot;pop&quot;: 221109,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 6815 
},
{
 &quot;date&quot;:           2890,
&quot;pce&quot;:         1341.3,
&quot;pop&quot;: 221303,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6386 
},
{
 &quot;date&quot;:           2921,
&quot;pce&quot;:         1335.2,
&quot;pop&quot;: 221477,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 6489 
},
{
 &quot;date&quot;:           2952,
&quot;pce&quot;:           1361,
&quot;pop&quot;: 221629,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 6318 
},
{
 &quot;date&quot;:           2980,
&quot;pce&quot;:         1383.6,
&quot;pop&quot;: 221792,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 6337 
},
{
 &quot;date&quot;:           3011,
&quot;pce&quot;:         1402.5,
&quot;pop&quot;: 221991,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 6180 
},
{
 &quot;date&quot;:           3041,
&quot;pce&quot;:         1418.2,
&quot;pop&quot;: 222176,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 6127 
},
{
 &quot;date&quot;:           3072,
&quot;pce&quot;:         1432.1,
&quot;pop&quot;: 222379,
&quot;psavert&quot;:            8.1,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 6028 
},
{
 &quot;date&quot;:           3102,
&quot;pce&quot;:         1433.2,
&quot;pop&quot;: 222585,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6309 
},
{
 &quot;date&quot;:           3133,
&quot;pce&quot;:         1453.4,
&quot;pop&quot;: 222805,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6080 
},
{
 &quot;date&quot;:           3164,
&quot;pce&quot;:         1459.4,
&quot;pop&quot;: 223053,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 6125 
},
{
 &quot;date&quot;:           3194,
&quot;pce&quot;:         1473.5,
&quot;pop&quot;: 223271,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 5947 
},
{
 &quot;date&quot;:           3225,
&quot;pce&quot;:         1487.1,
&quot;pop&quot;: 223477,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 6077 
},
{
 &quot;date&quot;:           3255,
&quot;pce&quot;:           1503,
&quot;pop&quot;: 223670,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 6228 
},
{
 &quot;date&quot;:           3286,
&quot;pce&quot;:         1508.9,
&quot;pop&quot;: 223865,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6109 
},
{
 &quot;date&quot;:           3317,
&quot;pce&quot;:         1524.4,
&quot;pop&quot;: 224053,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6173 
},
{
 &quot;date&quot;:           3345,
&quot;pce&quot;:         1537.7,
&quot;pop&quot;: 224235,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6109 
},
{
 &quot;date&quot;:           3376,
&quot;pce&quot;:         1545.1,
&quot;pop&quot;: 224438,
&quot;psavert&quot;:            9.2,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6069 
},
{
 &quot;date&quot;:           3406,
&quot;pce&quot;:         1565.5,
&quot;pop&quot;: 224632,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 5840 
},
{
 &quot;date&quot;:           3437,
&quot;pce&quot;:         1582.3,
&quot;pop&quot;: 224843,
&quot;psavert&quot;:            8.4,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 5959 
},
{
 &quot;date&quot;:           3467,
&quot;pce&quot;:         1592.6,
&quot;pop&quot;: 225055,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 5996 
},
{
 &quot;date&quot;:           3498,
&quot;pce&quot;:         1622.3,
&quot;pop&quot;: 225295,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 6320 
},
{
 &quot;date&quot;:           3529,
&quot;pce&quot;:         1640.8,
&quot;pop&quot;: 225547,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 6190 
},
{
 &quot;date&quot;:           3559,
&quot;pce&quot;:         1648.7,
&quot;pop&quot;: 225801,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            5.5,
&quot;unemploy&quot;: 6296 
},
{
 &quot;date&quot;:           3590,
&quot;pce&quot;:         1664.5,
&quot;pop&quot;: 226027,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 6238 
},
{
 &quot;date&quot;:           3620,
&quot;pce&quot;:         1673.5,
&quot;pop&quot;: 226243,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 6325 
},
{
 &quot;date&quot;:           3651,
&quot;pce&quot;:         1704.1,
&quot;pop&quot;: 226451,
&quot;psavert&quot;:            9.3,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 6683 
},
{
 &quot;date&quot;:           3682,
&quot;pce&quot;:         1708.2,
&quot;pop&quot;: 226656,
&quot;psavert&quot;:            9.6,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6702 
},
{
 &quot;date&quot;:           3711,
&quot;pce&quot;:         1714.9,
&quot;pop&quot;: 226849,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 6729 
},
{
 &quot;date&quot;:           3742,
&quot;pce&quot;:         1701.8,
&quot;pop&quot;: 227061,
&quot;psavert&quot;:           10.1,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 7358 
},
{
 &quot;date&quot;:           3772,
&quot;pce&quot;:         1706.6,
&quot;pop&quot;: 227251,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 7984 
},
{
 &quot;date&quot;:           3803,
&quot;pce&quot;:         1725.3,
&quot;pop&quot;: 227522,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 8098 
},
{
 &quot;date&quot;:           3833,
&quot;pce&quot;:         1753.6,
&quot;pop&quot;: 227726,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 8363 
},
{
 &quot;date&quot;:           3864,
&quot;pce&quot;:         1770.1,
&quot;pop&quot;: 227953,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 8281 
},
{
 &quot;date&quot;:           3895,
&quot;pce&quot;:         1786.6,
&quot;pop&quot;: 228186,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 8021 
},
{
 &quot;date&quot;:           3925,
&quot;pce&quot;:           1823,
&quot;pop&quot;: 228417,
&quot;psavert&quot;:           10.4,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 8088 
},
{
 &quot;date&quot;:           3956,
&quot;pce&quot;:           1833,
&quot;pop&quot;: 228612,
&quot;psavert&quot;:           10.9,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 8023 
},
{
 &quot;date&quot;:           3986,
&quot;pce&quot;:         1858.3,
&quot;pop&quot;: 228779,
&quot;psavert&quot;:           10.7,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 7718 
},
{
 &quot;date&quot;:           4017,
&quot;pce&quot;:         1877.7,
&quot;pop&quot;: 228937,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            7.4,
&quot;unemploy&quot;: 8071 
},
{
 &quot;date&quot;:           4048,
&quot;pce&quot;:         1892.2,
&quot;pop&quot;: 229071,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8051 
},
{
 &quot;date&quot;:           4076,
&quot;pce&quot;:         1911.3,
&quot;pop&quot;: 229224,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 7982 
},
{
 &quot;date&quot;:           4107,
&quot;pce&quot;:         1912.6,
&quot;pop&quot;: 229403,
&quot;psavert&quot;:            9.8,
&quot;uempmed&quot;:            7.4,
&quot;unemploy&quot;: 7869 
},
{
 &quot;date&quot;:           4137,
&quot;pce&quot;:         1921.7,
&quot;pop&quot;: 229575,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8174 
},
{
 &quot;date&quot;:           4168,
&quot;pce&quot;:         1942.3,
&quot;pop&quot;: 229761,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 8098 
},
{
 &quot;date&quot;:           4198,
&quot;pce&quot;:         1949.6,
&quot;pop&quot;: 229966,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 7863 
},
{
 &quot;date&quot;:           4229,
&quot;pce&quot;:         1973.7,
&quot;pop&quot;: 230187,
&quot;psavert&quot;:           11.2,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 8036 
},
{
 &quot;date&quot;:           4260,
&quot;pce&quot;:         1972.1,
&quot;pop&quot;: 230412,
&quot;psavert&quot;:           11.7,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8230 
},
{
 &quot;date&quot;:           4290,
&quot;pce&quot;:           1970,
&quot;pop&quot;: 230641,
&quot;psavert&quot;:           12.5,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8646 
},
{
 &quot;date&quot;:           4321,
&quot;pce&quot;:           1976,
&quot;pop&quot;: 230822,
&quot;psavert&quot;:           12.5,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 9029 
},
{
 &quot;date&quot;:           4351,
&quot;pce&quot;:         1993.6,
&quot;pop&quot;: 230989,
&quot;psavert&quot;:           11.7,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 9267 
},
{
 &quot;date&quot;:           4382,
&quot;pce&quot;:         2001.1,
&quot;pop&quot;: 231157,
&quot;psavert&quot;:           11.9,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 9397 
},
{
 &quot;date&quot;:           4413,
&quot;pce&quot;:         2024.9,
&quot;pop&quot;: 231313,
&quot;psavert&quot;:           11.3,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 9705 
},
{
 &quot;date&quot;:           4441,
&quot;pce&quot;:         2028.1,
&quot;pop&quot;: 231470,
&quot;psavert&quot;:           11.5,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 9895 
},
{
 &quot;date&quot;:           4472,
&quot;pce&quot;:         2030.5,
&quot;pop&quot;: 231645,
&quot;psavert&quot;:           12.2,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 10244 
},
{
 &quot;date&quot;:           4502,
&quot;pce&quot;:         2049.3,
&quot;pop&quot;: 231809,
&quot;psavert&quot;:           11.6,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 10335 
},
{
 &quot;date&quot;:           4533,
&quot;pce&quot;:         2053.5,
&quot;pop&quot;: 231992,
&quot;psavert&quot;:           11.5,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 10538 
},
{
 &quot;date&quot;:           4563,
&quot;pce&quot;:         2078.3,
&quot;pop&quot;: 232188,
&quot;psavert&quot;:           11.9,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 10849 
},
{
 &quot;date&quot;:           4594,
&quot;pce&quot;:         2086.9,
&quot;pop&quot;: 232392,
&quot;psavert&quot;:           11.7,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 10881 
},
{
 &quot;date&quot;:           4625,
&quot;pce&quot;:           2112,
&quot;pop&quot;: 232599,
&quot;psavert&quot;:           10.8,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 11217 
},
{
 &quot;date&quot;:           4655,
&quot;pce&quot;:         2133.8,
&quot;pop&quot;: 232816,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            9.7,
&quot;unemploy&quot;: 11529 
},
{
 &quot;date&quot;:           4686,
&quot;pce&quot;:         2158.1,
&quot;pop&quot;: 232993,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:             10,
&quot;unemploy&quot;: 11938 
},
{
 &quot;date&quot;:           4716,
&quot;pce&quot;:         2170.8,
&quot;pop&quot;: 233160,
&quot;psavert&quot;:            9.7,
&quot;uempmed&quot;:           10.2,
&quot;unemploy&quot;: 12051 
},
{
 &quot;date&quot;:           4747,
&quot;pce&quot;:         2183.6,
&quot;pop&quot;: 233322,
&quot;psavert&quot;:            9.9,
&quot;uempmed&quot;:           11.1,
&quot;unemploy&quot;: 11534 
},
{
 &quot;date&quot;:           4778,
&quot;pce&quot;:         2186.5,
&quot;pop&quot;: 233473,
&quot;psavert&quot;:             10,
&quot;uempmed&quot;:            9.8,
&quot;unemploy&quot;: 11545 
},
{
 &quot;date&quot;:           4806,
&quot;pce&quot;:         2212.2,
&quot;pop&quot;: 233613,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:           10.4,
&quot;unemploy&quot;: 11408 
},
{
 &quot;date&quot;:           4837,
&quot;pce&quot;:         2235.3,
&quot;pop&quot;: 233781,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:           10.9,
&quot;unemploy&quot;: 11268 
},
{
 &quot;date&quot;:           4867,
&quot;pce&quot;:         2254.7,
&quot;pop&quot;: 233922,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:           12.3,
&quot;unemploy&quot;: 11154 
},
{
 &quot;date&quot;:           4898,
&quot;pce&quot;:         2284.7,
&quot;pop&quot;: 234118,
&quot;psavert&quot;:            8.1,
&quot;uempmed&quot;:           11.3,
&quot;unemploy&quot;: 11246 
},
{
 &quot;date&quot;:           4928,
&quot;pce&quot;:         2313.2,
&quot;pop&quot;: 234307,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:           10.1,
&quot;unemploy&quot;: 10548 
},
{
 &quot;date&quot;:           4959,
&quot;pce&quot;:         2329.2,
&quot;pop&quot;: 234501,
&quot;psavert&quot;:              8,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 10623 
},
{
 &quot;date&quot;:           4990,
&quot;pce&quot;:         2343.4,
&quot;pop&quot;: 234701,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 10282 
},
{
 &quot;date&quot;:           5020,
&quot;pce&quot;:         2366.2,
&quot;pop&quot;: 234907,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:            9.4,
&quot;unemploy&quot;: 9887 
},
{
 &quot;date&quot;:           5051,
&quot;pce&quot;:           2375,
&quot;pop&quot;: 235078,
&quot;psavert&quot;:            9.2,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 9499 
},
{
 &quot;date&quot;:           5081,
&quot;pce&quot;:         2402.7,
&quot;pop&quot;: 235235,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 9331 
},
{
 &quot;date&quot;:           5112,
&quot;pce&quot;:         2428.6,
&quot;pop&quot;: 235385,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 9008 
},
{
 &quot;date&quot;:           5143,
&quot;pce&quot;:         2412.8,
&quot;pop&quot;: 235527,
&quot;psavert&quot;:           10.8,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8791 
},
{
 &quot;date&quot;:           5172,
&quot;pce&quot;:         2441.3,
&quot;pop&quot;: 235675,
&quot;psavert&quot;:           10.6,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8746 
},
{
 &quot;date&quot;:           5203,
&quot;pce&quot;:         2467.6,
&quot;pop&quot;: 235839,
&quot;psavert&quot;:           10.8,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 8762 
},
{
 &quot;date&quot;:           5233,
&quot;pce&quot;:           2485,
&quot;pop&quot;: 235993,
&quot;psavert&quot;:           10.5,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 8456 
},
{
 &quot;date&quot;:           5264,
&quot;pce&quot;:         2506.5,
&quot;pop&quot;: 236160,
&quot;psavert&quot;:           10.6,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 8226 
},
{
 &quot;date&quot;:           5294,
&quot;pce&quot;:         2505.7,
&quot;pop&quot;: 236348,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 8537 
},
{
 &quot;date&quot;:           5325,
&quot;pce&quot;:         2523.8,
&quot;pop&quot;: 236549,
&quot;psavert&quot;:           11.3,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 8519 
},
{
 &quot;date&quot;:           5356,
&quot;pce&quot;:         2545.4,
&quot;pop&quot;: 236760,
&quot;psavert&quot;:           11.2,
&quot;uempmed&quot;:            7.6,
&quot;unemploy&quot;: 8367 
},
{
 &quot;date&quot;:           5386,
&quot;pce&quot;:         2543.6,
&quot;pop&quot;: 236976,
&quot;psavert&quot;:           11.4,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 8381 
},
{
 &quot;date&quot;:           5417,
&quot;pce&quot;:           2584,
&quot;pop&quot;: 237159,
&quot;psavert&quot;:           10.6,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 8198 
},
{
 &quot;date&quot;:           5447,
&quot;pce&quot;:         2595.3,
&quot;pop&quot;: 237316,
&quot;psavert&quot;:             11,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 8358 
},
{
 &quot;date&quot;:           5478,
&quot;pce&quot;:         2629.6,
&quot;pop&quot;: 237468,
&quot;psavert&quot;:           10.3,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8423 
},
{
 &quot;date&quot;:           5509,
&quot;pce&quot;:         2650.5,
&quot;pop&quot;: 237602,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8321 
},
{
 &quot;date&quot;:           5537,
&quot;pce&quot;:         2657.1,
&quot;pop&quot;: 237732,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8339 
},
{
 &quot;date&quot;:           5568,
&quot;pce&quot;:         2668.8,
&quot;pop&quot;: 237900,
&quot;psavert&quot;:           10.1,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8395 
},
{
 &quot;date&quot;:           5598,
&quot;pce&quot;:           2705,
&quot;pop&quot;: 238074,
&quot;psavert&quot;:           11.1,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8302 
},
{
 &quot;date&quot;:           5629,
&quot;pce&quot;:         2696.4,
&quot;pop&quot;: 238270,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 8460 
},
{
 &quot;date&quot;:           5659,
&quot;pce&quot;:         2720.5,
&quot;pop&quot;: 238466,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8513 
},
{
 &quot;date&quot;:           5690,
&quot;pce&quot;:           2756,
&quot;pop&quot;: 238679,
&quot;psavert&quot;:              8,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8196 
},
{
 &quot;date&quot;:           5721,
&quot;pce&quot;:         2799.7,
&quot;pop&quot;: 238898,
&quot;psavert&quot;:            6.8,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8248 
},
{
 &quot;date&quot;:           5751,
&quot;pce&quot;:         2762.3,
&quot;pop&quot;: 239113,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8298 
},
{
 &quot;date&quot;:           5782,
&quot;pce&quot;:         2778.7,
&quot;pop&quot;: 239307,
&quot;psavert&quot;:            8.5,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 8128 
},
{
 &quot;date&quot;:           5812,
&quot;pce&quot;:         2819.1,
&quot;pop&quot;: 239477,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8138 
},
{
 &quot;date&quot;:           5843,
&quot;pce&quot;:         2833.5,
&quot;pop&quot;: 239638,
&quot;psavert&quot;:            8.2,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 7795 
},
{
 &quot;date&quot;:           5874,
&quot;pce&quot;:         2826.7,
&quot;pop&quot;: 239788,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8402 
},
{
 &quot;date&quot;:           5902,
&quot;pce&quot;:         2830.7,
&quot;pop&quot;: 239928,
&quot;psavert&quot;:            9.5,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8383 
},
{
 &quot;date&quot;:           5933,
&quot;pce&quot;:         2843.8,
&quot;pop&quot;: 240094,
&quot;psavert&quot;:            9.1,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 8364 
},
{
 &quot;date&quot;:           5963,
&quot;pce&quot;:         2867.8,
&quot;pop&quot;: 240271,
&quot;psavert&quot;:            8.7,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8439 
},
{
 &quot;date&quot;:           5994,
&quot;pce&quot;:         2874.2,
&quot;pop&quot;: 240459,
&quot;psavert&quot;:            8.9,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 8508 
},
{
 &quot;date&quot;:           6024,
&quot;pce&quot;:         2895.9,
&quot;pop&quot;: 240651,
&quot;psavert&quot;:            8.6,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8319 
},
{
 &quot;date&quot;:           6055,
&quot;pce&quot;:         2914.8,
&quot;pop&quot;: 240854,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8135 
},
{
 &quot;date&quot;:           6086,
&quot;pce&quot;:         2989.8,
&quot;pop&quot;: 241068,
&quot;psavert&quot;:            6.4,
&quot;uempmed&quot;:            7.4,
&quot;unemploy&quot;: 8310 
},
{
 &quot;date&quot;:           6116,
&quot;pce&quot;:         2951.6,
&quot;pop&quot;: 241274,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 8243 
},
{
 &quot;date&quot;:           6147,
&quot;pce&quot;:         2948.5,
&quot;pop&quot;: 241467,
&quot;psavert&quot;:            8.1,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 8159 
},
{
 &quot;date&quot;:           6177,
&quot;pce&quot;:         3019.5,
&quot;pop&quot;: 241620,
&quot;psavert&quot;:            5.9,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 7883 
},
{
 &quot;date&quot;:           6208,
&quot;pce&quot;:         2959.7,
&quot;pop&quot;: 241784,
&quot;psavert&quot;:            8.8,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 7892 
},
{
 &quot;date&quot;:           6239,
&quot;pce&quot;:         3026.7,
&quot;pop&quot;: 241930,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 7865 
},
{
 &quot;date&quot;:           6267,
&quot;pce&quot;:         3037.6,
&quot;pop&quot;: 242079,
&quot;psavert&quot;:            7.7,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 7862 
},
{
 &quot;date&quot;:           6298,
&quot;pce&quot;:         3061.2,
&quot;pop&quot;: 242252,
&quot;psavert&quot;:            3.5,
&quot;uempmed&quot;:            7.1,
&quot;unemploy&quot;: 7542 
},
{
 &quot;date&quot;:           6328,
&quot;pce&quot;:         3070.1,
&quot;pop&quot;: 242423,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 7574 
},
{
 &quot;date&quot;:           6359,
&quot;pce&quot;:         3094.8,
&quot;pop&quot;: 242608,
&quot;psavert&quot;:            6.7,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 7398 
},
{
 &quot;date&quot;:           6389,
&quot;pce&quot;:         3118.2,
&quot;pop&quot;: 242804,
&quot;psavert&quot;:            6.5,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 7268 
},
{
 &quot;date&quot;:           6420,
&quot;pce&quot;:         3155.2,
&quot;pop&quot;: 243012,
&quot;psavert&quot;:            6.2,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 7261 
},
{
 &quot;date&quot;:           6451,
&quot;pce&quot;:         3151.3,
&quot;pop&quot;: 243223,
&quot;psavert&quot;:            6.7,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 7102 
},
{
 &quot;date&quot;:           6481,
&quot;pce&quot;:         3159.6,
&quot;pop&quot;: 243446,
&quot;psavert&quot;:            7.4,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 7227 
},
{
 &quot;date&quot;:           6512,
&quot;pce&quot;:         3169.3,
&quot;pop&quot;: 243639,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 7035 
},
{
 &quot;date&quot;:           6542,
&quot;pce&quot;:           3199,
&quot;pop&quot;: 243809,
&quot;psavert&quot;:            7.7,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 6936 
},
{
 &quot;date&quot;:           6573,
&quot;pce&quot;:         3238.6,
&quot;pop&quot;: 243981,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 6953 
},
{
 &quot;date&quot;:           6604,
&quot;pce&quot;:         3246.2,
&quot;pop&quot;: 244131,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 6929 
},
{
 &quot;date&quot;:           6633,
&quot;pce&quot;:         3285.5,
&quot;pop&quot;: 244279,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 6876 
},
{
 &quot;date&quot;:           6664,
&quot;pce&quot;:           3288,
&quot;pop&quot;: 244445,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6601 
},
{
 &quot;date&quot;:           6694,
&quot;pce&quot;:         3318.5,
&quot;pop&quot;: 244610,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6779 
},
{
 &quot;date&quot;:           6725,
&quot;pce&quot;:         3342.7,
&quot;pop&quot;: 244806,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6546 
},
{
 &quot;date&quot;:           6755,
&quot;pce&quot;:         3365.6,
&quot;pop&quot;: 245021,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 6605 
},
{
 &quot;date&quot;:           6786,
&quot;pce&quot;:           3390,
&quot;pop&quot;: 245240,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6843 
},
{
 &quot;date&quot;:           6817,
&quot;pce&quot;:         3396.6,
&quot;pop&quot;: 245464,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 6604 
},
{
 &quot;date&quot;:           6847,
&quot;pce&quot;:         3436.3,
&quot;pop&quot;: 245693,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 6568 
},
{
 &quot;date&quot;:           6878,
&quot;pce&quot;:         3452.4,
&quot;pop&quot;: 245884,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 6537 
},
{
 &quot;date&quot;:           6908,
&quot;pce&quot;:         3482.8,
&quot;pop&quot;: 246056,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6518 
},
{
 &quot;date&quot;:           6939,
&quot;pce&quot;:         3505.3,
&quot;pop&quot;: 246224,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 6682 
},
{
 &quot;date&quot;:           6970,
&quot;pce&quot;:         3509.3,
&quot;pop&quot;: 246378,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6359 
},
{
 &quot;date&quot;:           6998,
&quot;pce&quot;:         3519.3,
&quot;pop&quot;: 246530,
&quot;psavert&quot;:            8.3,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6205 
},
{
 &quot;date&quot;:           7029,
&quot;pce&quot;:         3563.2,
&quot;pop&quot;: 246721,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6468 
},
{
 &quot;date&quot;:           7059,
&quot;pce&quot;:         3571.8,
&quot;pop&quot;: 246906,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 6375 
},
{
 &quot;date&quot;:           7090,
&quot;pce&quot;:         3586.7,
&quot;pop&quot;: 247114,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6577 
},
{
 &quot;date&quot;:           7120,
&quot;pce&quot;:         3606.4,
&quot;pop&quot;: 247342,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 6495 
},
{
 &quot;date&quot;:           7151,
&quot;pce&quot;:         3642.2,
&quot;pop&quot;: 247573,
&quot;psavert&quot;:            6.4,
&quot;uempmed&quot;:              5,
&quot;unemploy&quot;: 6511 
},
{
 &quot;date&quot;:           7182,
&quot;pce&quot;:         3644.2,
&quot;pop&quot;: 247816,
&quot;psavert&quot;:            6.6,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 6590 
},
{
 &quot;date&quot;:           7212,
&quot;pce&quot;:           3657,
&quot;pop&quot;: 248067,
&quot;psavert&quot;:            6.8,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 6630 
},
{
 &quot;date&quot;:           7243,
&quot;pce&quot;:         3667.6,
&quot;pop&quot;: 248281,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 6725 
},
{
 &quot;date&quot;:           7273,
&quot;pce&quot;:         3708.9,
&quot;pop&quot;: 248479,
&quot;psavert&quot;:            6.5,
&quot;uempmed&quot;:            4.9,
&quot;unemploy&quot;: 6667 
},
{
 &quot;date&quot;:           7304,
&quot;pce&quot;:         3754.5,
&quot;pop&quot;: 248659,
&quot;psavert&quot;:            6.6,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 6752 
},
{
 &quot;date&quot;:           7335,
&quot;pce&quot;:         3752.2,
&quot;pop&quot;: 248827,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            5.3,
&quot;unemploy&quot;: 6651 
},
{
 &quot;date&quot;:           7363,
&quot;pce&quot;:           3781,
&quot;pop&quot;: 249012,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            5.1,
&quot;unemploy&quot;: 6598 
},
{
 &quot;date&quot;:           7394,
&quot;pce&quot;:         3800.5,
&quot;pop&quot;: 249306,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            4.8,
&quot;unemploy&quot;: 6797 
},
{
 &quot;date&quot;:           7424,
&quot;pce&quot;:         3808.6,
&quot;pop&quot;: 249565,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 6742 
},
{
 &quot;date&quot;:           7455,
&quot;pce&quot;:         3838.5,
&quot;pop&quot;: 249849,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 6590 
},
{
 &quot;date&quot;:           7485,
&quot;pce&quot;:         3855.1,
&quot;pop&quot;: 250132,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 6922 
},
{
 &quot;date&quot;:           7516,
&quot;pce&quot;:           3881,
&quot;pop&quot;: 250439,
&quot;psavert&quot;:            6.7,
&quot;uempmed&quot;:            5.4,
&quot;unemploy&quot;: 7188 
},
{
 &quot;date&quot;:           7547,
&quot;pce&quot;:         3902.7,
&quot;pop&quot;: 250751,
&quot;psavert&quot;:            6.7,
&quot;uempmed&quot;:            5.6,
&quot;unemploy&quot;: 7368 
},
{
 &quot;date&quot;:           7577,
&quot;pce&quot;:         3902.9,
&quot;pop&quot;: 251057,
&quot;psavert&quot;:            6.6,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 7459 
},
{
 &quot;date&quot;:           7608,
&quot;pce&quot;:         3905.6,
&quot;pop&quot;: 251346,
&quot;psavert&quot;:            6.7,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 7764 
},
{
 &quot;date&quot;:           7638,
&quot;pce&quot;:         3896.6,
&quot;pop&quot;: 251626,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 7901 
},
{
 &quot;date&quot;:           7669,
&quot;pce&quot;:         3879.3,
&quot;pop&quot;: 251889,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 8015 
},
{
 &quot;date&quot;:           7700,
&quot;pce&quot;:         3907.7,
&quot;pop&quot;: 252135,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 8265 
},
{
 &quot;date&quot;:           7728,
&quot;pce&quot;:         3955.6,
&quot;pop&quot;: 252372,
&quot;psavert&quot;:            6.6,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 8586 
},
{
 &quot;date&quot;:           7759,
&quot;pce&quot;:         3950.5,
&quot;pop&quot;: 252643,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 8439 
},
{
 &quot;date&quot;:           7789,
&quot;pce&quot;:         3976.8,
&quot;pop&quot;: 252913,
&quot;psavert&quot;:            6.9,
&quot;uempmed&quot;:            6.4,
&quot;unemploy&quot;: 8736 
},
{
 &quot;date&quot;:           7820,
&quot;pce&quot;:         3983.6,
&quot;pop&quot;: 253207,
&quot;psavert&quot;:            7.4,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 8692 
},
{
 &quot;date&quot;:           7850,
&quot;pce&quot;:         4008.4,
&quot;pop&quot;: 253493,
&quot;psavert&quot;:            6.8,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 8586 
},
{
 &quot;date&quot;:           7881,
&quot;pce&quot;:         4011.3,
&quot;pop&quot;: 253807,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 8666 
},
{
 &quot;date&quot;:           7912,
&quot;pce&quot;:         4027.3,
&quot;pop&quot;: 254126,
&quot;psavert&quot;:            7.2,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 8722 
},
{
 &quot;date&quot;:           7942,
&quot;pce&quot;:         4020.1,
&quot;pop&quot;: 254435,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 8842 
},
{
 &quot;date&quot;:           7973,
&quot;pce&quot;:         4048.2,
&quot;pop&quot;: 254718,
&quot;psavert&quot;:            7.3,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 8931 
},
{
 &quot;date&quot;:           8003,
&quot;pce&quot;:           4064,
&quot;pop&quot;: 254964,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 9198 
},
{
 &quot;date&quot;:           8034,
&quot;pce&quot;:         4128.2,
&quot;pop&quot;: 255214,
&quot;psavert&quot;:            7.4,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 9283 
},
{
 &quot;date&quot;:           8065,
&quot;pce&quot;:         4141.8,
&quot;pop&quot;: 255448,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 9454 
},
{
 &quot;date&quot;:           8094,
&quot;pce&quot;:         4157.6,
&quot;pop&quot;: 255703,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 9460 
},
{
 &quot;date&quot;:           8125,
&quot;pce&quot;:         4169.8,
&quot;pop&quot;: 255992,
&quot;psavert&quot;:              8,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 9415 
},
{
 &quot;date&quot;:           8155,
&quot;pce&quot;:         4195.5,
&quot;pop&quot;: 256285,
&quot;psavert&quot;:            7.9,
&quot;uempmed&quot;:            8.8,
&quot;unemploy&quot;: 9744 
},
{
 &quot;date&quot;:           8186,
&quot;pce&quot;:         4213.8,
&quot;pop&quot;: 256589,
&quot;psavert&quot;:            7.8,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 10040 
},
{
 &quot;date&quot;:           8216,
&quot;pce&quot;:         4241.8,
&quot;pop&quot;: 256894,
&quot;psavert&quot;:            7.5,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 9850 
},
{
 &quot;date&quot;:           8247,
&quot;pce&quot;:         4258.8,
&quot;pop&quot;: 257232,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            8.8,
&quot;unemploy&quot;: 9787 
},
{
 &quot;date&quot;:           8278,
&quot;pce&quot;:         4292.5,
&quot;pop&quot;: 257548,
&quot;psavert&quot;:            6.9,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 9781 
},
{
 &quot;date&quot;:           8308,
&quot;pce&quot;:         4320.2,
&quot;pop&quot;: 257861,
&quot;psavert&quot;:            7.1,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 9398 
},
{
 &quot;date&quot;:           8339,
&quot;pce&quot;:         4334.3,
&quot;pop&quot;: 258147,
&quot;psavert&quot;:              7,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 9565 
},
{
 &quot;date&quot;:           8369,
&quot;pce&quot;:         4368.8,
&quot;pop&quot;: 258413,
&quot;psavert&quot;:            9.4,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 9557 
},
{
 &quot;date&quot;:           8400,
&quot;pce&quot;:         4371.5,
&quot;pop&quot;: 258679,
&quot;psavert&quot;:            5.8,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 9325 
},
{
 &quot;date&quot;:           8431,
&quot;pce&quot;:           4385,
&quot;pop&quot;: 258919,
&quot;psavert&quot;:            5.6,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 9183 
},
{
 &quot;date&quot;:           8459,
&quot;pce&quot;:         4381.5,
&quot;pop&quot;: 259152,
&quot;psavert&quot;:            5.6,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 9056 
},
{
 &quot;date&quot;:           8490,
&quot;pce&quot;:         4422.5,
&quot;pop&quot;: 259414,
&quot;psavert&quot;:            6.4,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 9110 
},
{
 &quot;date&quot;:           8520,
&quot;pce&quot;:         4450.9,
&quot;pop&quot;: 259680,
&quot;psavert&quot;:            6.3,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 9149 
},
{
 &quot;date&quot;:           8551,
&quot;pce&quot;:         4466.7,
&quot;pop&quot;: 259963,
&quot;psavert&quot;:            5.9,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 9121 
},
{
 &quot;date&quot;:           8581,
&quot;pce&quot;:         4493.8,
&quot;pop&quot;: 260255,
&quot;psavert&quot;:            5.4,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 8930 
},
{
 &quot;date&quot;:           8612,
&quot;pce&quot;:         4504.3,
&quot;pop&quot;: 260566,
&quot;psavert&quot;:            5.6,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 8763 
},
{
 &quot;date&quot;:           8643,
&quot;pce&quot;:           4534,
&quot;pop&quot;: 260867,
&quot;psavert&quot;:              5,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8714 
},
{
 &quot;date&quot;:           8673,
&quot;pce&quot;:         4554.8,
&quot;pop&quot;: 261163,
&quot;psavert&quot;:              5,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 8750 
},
{
 &quot;date&quot;:           8704,
&quot;pce&quot;:         4575.9,
&quot;pop&quot;: 261425,
&quot;psavert&quot;:              5,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8542 
},
{
 &quot;date&quot;:           8734,
&quot;pce&quot;:         4593.9,
&quot;pop&quot;: 261674,
&quot;psavert&quot;:            7.6,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8477 
},
{
 &quot;date&quot;:           8765,
&quot;pce&quot;:         4608.5,
&quot;pop&quot;: 261919,
&quot;psavert&quot;:              4,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 8630 
},
{
 &quot;date&quot;:           8796,
&quot;pce&quot;:         4655.7,
&quot;pop&quot;: 262123,
&quot;psavert&quot;:            3.9,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 8583 
},
{
 &quot;date&quot;:           8824,
&quot;pce&quot;:         4667.5,
&quot;pop&quot;: 262352,
&quot;psavert&quot;:            4.3,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 8470 
},
{
 &quot;date&quot;:           8855,
&quot;pce&quot;:         4690.3,
&quot;pop&quot;: 262631,
&quot;psavert&quot;:            4.2,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 8331 
},
{
 &quot;date&quot;:           8885,
&quot;pce&quot;:         4688.3,
&quot;pop&quot;: 262877,
&quot;psavert&quot;:            5.8,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7915 
},
{
 &quot;date&quot;:           8916,
&quot;pce&quot;:         4729.9,
&quot;pop&quot;: 263152,
&quot;psavert&quot;:            5.1,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 7927 
},
{
 &quot;date&quot;:           8946,
&quot;pce&quot;:         4745.4,
&quot;pop&quot;: 263436,
&quot;psavert&quot;:            5.1,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7946 
},
{
 &quot;date&quot;:           8977,
&quot;pce&quot;:         4789.2,
&quot;pop&quot;: 263724,
&quot;psavert&quot;:            4.7,
&quot;uempmed&quot;:            8.9,
&quot;unemploy&quot;: 7933 
},
{
 &quot;date&quot;:           9008,
&quot;pce&quot;:         4801.2,
&quot;pop&quot;: 264017,
&quot;psavert&quot;:              5,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7734 
},
{
 &quot;date&quot;:           9038,
&quot;pce&quot;:         4836.2,
&quot;pop&quot;: 264301,
&quot;psavert&quot;:            5.3,
&quot;uempmed&quot;:             10,
&quot;unemploy&quot;: 7632 
},
{
 &quot;date&quot;:           9069,
&quot;pce&quot;:         4846.5,
&quot;pop&quot;: 264559,
&quot;psavert&quot;:            5.2,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7375 
},
{
 &quot;date&quot;:           9099,
&quot;pce&quot;:         4860.9,
&quot;pop&quot;: 264804,
&quot;psavert&quot;:            5.3,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 7230 
},
{
 &quot;date&quot;:           9130,
&quot;pce&quot;:         4869.3,
&quot;pop&quot;: 265044,
&quot;psavert&quot;:            5.6,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 7375 
},
{
 &quot;date&quot;:           9161,
&quot;pce&quot;:         4867.4,
&quot;pop&quot;: 265270,
&quot;psavert&quot;:            5.9,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 7187 
},
{
 &quot;date&quot;:           9189,
&quot;pce&quot;:         4900.5,
&quot;pop&quot;: 265495,
&quot;psavert&quot;:            5.5,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7153 
},
{
 &quot;date&quot;:           9220,
&quot;pce&quot;:         4904.2,
&quot;pop&quot;: 265755,
&quot;psavert&quot;:            4.8,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7645 
},
{
 &quot;date&quot;:           9250,
&quot;pce&quot;:         4946.1,
&quot;pop&quot;: 265998,
&quot;psavert&quot;:            4.9,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 7430 
},
{
 &quot;date&quot;:           9281,
&quot;pce&quot;:         4989.8,
&quot;pop&quot;: 266270,
&quot;psavert&quot;:            4.4,
&quot;uempmed&quot;:            7.9,
&quot;unemploy&quot;: 7427 
},
{
 &quot;date&quot;:           9311,
&quot;pce&quot;:         4982.7,
&quot;pop&quot;: 266557,
&quot;psavert&quot;:            4.6,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7527 
},
{
 &quot;date&quot;:           9342,
&quot;pce&quot;:           5018,
&quot;pop&quot;: 266843,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7484 
},
{
 &quot;date&quot;:           9373,
&quot;pce&quot;:         5032.5,
&quot;pop&quot;: 267152,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            7.9,
&quot;unemploy&quot;: 7478 
},
{
 &quot;date&quot;:           9403,
&quot;pce&quot;:         5024.5,
&quot;pop&quot;: 267456,
&quot;psavert&quot;:            4.4,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 7328 
},
{
 &quot;date&quot;:           9434,
&quot;pce&quot;:         5065.8,
&quot;pop&quot;: 267715,
&quot;psavert&quot;:            3.9,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 7426 
},
{
 &quot;date&quot;:           9464,
&quot;pce&quot;:         5108.8,
&quot;pop&quot;: 267943,
&quot;psavert&quot;:            3.6,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7423 
},
{
 &quot;date&quot;:           9495,
&quot;pce&quot;:           5098,
&quot;pop&quot;: 268151,
&quot;psavert&quot;:            4.2,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7491 
},
{
 &quot;date&quot;:           9526,
&quot;pce&quot;:         5145.2,
&quot;pop&quot;: 268364,
&quot;psavert&quot;:            4.3,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 7313 
},
{
 &quot;date&quot;:           9555,
&quot;pce&quot;:         5185.1,
&quot;pop&quot;: 268595,
&quot;psavert&quot;:            4.2,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7318 
},
{
 &quot;date&quot;:           9586,
&quot;pce&quot;:         5219.6,
&quot;pop&quot;: 268853,
&quot;psavert&quot;:            3.1,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 7415 
},
{
 &quot;date&quot;:           9616,
&quot;pce&quot;:         5234.8,
&quot;pop&quot;: 269108,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 7423 
},
{
 &quot;date&quot;:           9647,
&quot;pce&quot;:         5241.6,
&quot;pop&quot;: 269386,
&quot;psavert&quot;:            4.5,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7095 
},
{
 &quot;date&quot;:           9677,
&quot;pce&quot;:         5263.6,
&quot;pop&quot;: 269667,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7337 
},
{
 &quot;date&quot;:           9708,
&quot;pce&quot;:         5287.5,
&quot;pop&quot;: 269976,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 6882 
},
{
 &quot;date&quot;:           9739,
&quot;pce&quot;:         5308.2,
&quot;pop&quot;: 270284,
&quot;psavert&quot;:            4.1,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 6979 
},
{
 &quot;date&quot;:           9769,
&quot;pce&quot;:         5340.1,
&quot;pop&quot;: 270581,
&quot;psavert&quot;:            3.8,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 7031 
},
{
 &quot;date&quot;:           9800,
&quot;pce&quot;:         5365.5,
&quot;pop&quot;: 270878,
&quot;psavert&quot;:            3.8,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 7236 
},
{
 &quot;date&quot;:           9830,
&quot;pce&quot;:         5392.7,
&quot;pop&quot;: 271125,
&quot;psavert&quot;:            3.8,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 7253 
},
{
 &quot;date&quot;:           9861,
&quot;pce&quot;:         5419.9,
&quot;pop&quot;: 271360,
&quot;psavert&quot;:            3.7,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 7158 
},
{
 &quot;date&quot;:           9892,
&quot;pce&quot;:         5453.9,
&quot;pop&quot;: 271585,
&quot;psavert&quot;:            3.5,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 7102 
},
{
 &quot;date&quot;:           9920,
&quot;pce&quot;:         5472.6,
&quot;pop&quot;: 271821,
&quot;psavert&quot;:            3.7,
&quot;uempmed&quot;:            7.9,
&quot;unemploy&quot;: 7000 
},
{
 &quot;date&quot;:           9951,
&quot;pce&quot;:         5473.4,
&quot;pop&quot;: 272083,
&quot;psavert&quot;:            3.8,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 6873 
},
{
 &quot;date&quot;:           9981,
&quot;pce&quot;:         5474.4,
&quot;pop&quot;: 272342,
&quot;psavert&quot;:              4,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 6655 
},
{
 &quot;date&quot;:          10012,
&quot;pce&quot;:         5506.1,
&quot;pop&quot;: 272622,
&quot;psavert&quot;:            3.9,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 6799 
},
{
 &quot;date&quot;:          10042,
&quot;pce&quot;:           5565,
&quot;pop&quot;: 272912,
&quot;psavert&quot;:            3.3,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 6655 
},
{
 &quot;date&quot;:          10073,
&quot;pce&quot;:         5596.7,
&quot;pop&quot;: 273237,
&quot;psavert&quot;:            3.3,
&quot;uempmed&quot;:            7.8,
&quot;unemploy&quot;: 6608 
},
{
 &quot;date&quot;:          10104,
&quot;pce&quot;:         5607.6,
&quot;pop&quot;: 273553,
&quot;psavert&quot;:            3.6,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 6656 
},
{
 &quot;date&quot;:          10134,
&quot;pce&quot;:         5639.2,
&quot;pop&quot;: 273852,
&quot;psavert&quot;:            3.5,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 6454 
},
{
 &quot;date&quot;:          10165,
&quot;pce&quot;:         5666.1,
&quot;pop&quot;: 274126,
&quot;psavert&quot;:            3.7,
&quot;uempmed&quot;:            7.6,
&quot;unemploy&quot;: 6308 
},
{
 &quot;date&quot;:          10195,
&quot;pce&quot;:           5694,
&quot;pop&quot;: 274372,
&quot;psavert&quot;:            3.8,
&quot;uempmed&quot;:            7.5,
&quot;unemploy&quot;: 6476 
},
{
 &quot;date&quot;:          10226,
&quot;pce&quot;:         5698.7,
&quot;pop&quot;: 274626,
&quot;psavert&quot;:            4.6,
&quot;uempmed&quot;:            7.4,
&quot;unemploy&quot;: 6368 
},
{
 &quot;date&quot;:          10257,
&quot;pce&quot;:         5736.6,
&quot;pop&quot;: 274838,
&quot;psavert&quot;:            4.6,
&quot;uempmed&quot;:              7,
&quot;unemploy&quot;: 6306 
},
{
 &quot;date&quot;:          10285,
&quot;pce&quot;:         5764.8,
&quot;pop&quot;: 275047,
&quot;psavert&quot;:            4.7,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6422 
},
{
 &quot;date&quot;:          10316,
&quot;pce&quot;:         5788.9,
&quot;pop&quot;: 275304,
&quot;psavert&quot;:            4.7,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 5941 
},
{
 &quot;date&quot;:          10346,
&quot;pce&quot;:         5842.9,
&quot;pop&quot;: 275564,
&quot;psavert&quot;:            4.4,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 6047 
},
{
 &quot;date&quot;:          10377,
&quot;pce&quot;:         5870.8,
&quot;pop&quot;: 275836,
&quot;psavert&quot;:            4.4,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 6212 
},
{
 &quot;date&quot;:          10407,
&quot;pce&quot;:         5887.4,
&quot;pop&quot;: 276115,
&quot;psavert&quot;:            4.5,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 6259 
},
{
 &quot;date&quot;:          10438,
&quot;pce&quot;:         5928.8,
&quot;pop&quot;: 276418,
&quot;psavert&quot;:            4.3,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6179 
},
{
 &quot;date&quot;:          10469,
&quot;pce&quot;:         5956.3,
&quot;pop&quot;: 276714,
&quot;psavert&quot;:            4.2,
&quot;uempmed&quot;:            6.7,
&quot;unemploy&quot;: 6300 
},
{
 &quot;date&quot;:          10499,
&quot;pce&quot;:         5995.2,
&quot;pop&quot;: 277003,
&quot;psavert&quot;:            3.9,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6280 
},
{
 &quot;date&quot;:          10530,
&quot;pce&quot;:         6018.5,
&quot;pop&quot;: 277277,
&quot;psavert&quot;:              4,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 6100 
},
{
 &quot;date&quot;:          10560,
&quot;pce&quot;:         6064.8,
&quot;pop&quot;: 277526,
&quot;psavert&quot;:            3.5,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6032 
},
{
 &quot;date&quot;:          10591,
&quot;pce&quot;:         6067.4,
&quot;pop&quot;: 277790,
&quot;psavert&quot;:              4,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 5976 
},
{
 &quot;date&quot;:          10622,
&quot;pce&quot;:         6099.7,
&quot;pop&quot;: 277992,
&quot;psavert&quot;:            3.7,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6111 
},
{
 &quot;date&quot;:          10650,
&quot;pce&quot;:           6138,
&quot;pop&quot;: 278198,
&quot;psavert&quot;:            3.3,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 5783 
},
{
 &quot;date&quot;:          10681,
&quot;pce&quot;:         6202.5,
&quot;pop&quot;: 278451,
&quot;psavert&quot;:            2.5,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 6004 
},
{
 &quot;date&quot;:          10711,
&quot;pce&quot;:         6245.1,
&quot;pop&quot;: 278717,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 5796 
},
{
 &quot;date&quot;:          10742,
&quot;pce&quot;:         6264.1,
&quot;pop&quot;: 279001,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 5951 
},
{
 &quot;date&quot;:          10772,
&quot;pce&quot;:         6297.3,
&quot;pop&quot;: 279295,
&quot;psavert&quot;:            1.9,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6025 
},
{
 &quot;date&quot;:          10803,
&quot;pce&quot;:         6338.6,
&quot;pop&quot;: 279602,
&quot;psavert&quot;:            1.8,
&quot;uempmed&quot;:            6.5,
&quot;unemploy&quot;: 5838 
},
{
 &quot;date&quot;:          10834,
&quot;pce&quot;:         6375.7,
&quot;pop&quot;: 279903,
&quot;psavert&quot;:            1.4,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 5915 
},
{
 &quot;date&quot;:          10864,
&quot;pce&quot;:         6396.7,
&quot;pop&quot;: 280203,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 5778 
},
{
 &quot;date&quot;:          10895,
&quot;pce&quot;:         6433.2,
&quot;pop&quot;: 280471,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:            6.2,
&quot;unemploy&quot;: 5716 
},
{
 &quot;date&quot;:          10925,
&quot;pce&quot;:         6531.3,
&quot;pop&quot;: 280716,
&quot;psavert&quot;:            1.6,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 5653 
},
{
 &quot;date&quot;:          10956,
&quot;pce&quot;:           6538,
&quot;pop&quot;: 280976,
&quot;psavert&quot;:            2.9,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 5708 
},
{
 &quot;date&quot;:          10987,
&quot;pce&quot;:         6618.5,
&quot;pop&quot;: 281190,
&quot;psavert&quot;:            2.4,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 5858 
},
{
 &quot;date&quot;:          11016,
&quot;pce&quot;:         6685.3,
&quot;pop&quot;: 281409,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 5733 
},
{
 &quot;date&quot;:          11047,
&quot;pce&quot;:         6664.2,
&quot;pop&quot;: 281653,
&quot;psavert&quot;:            2.4,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 5481 
},
{
 &quot;date&quot;:          11077,
&quot;pce&quot;:           6688,
&quot;pop&quot;: 281891,
&quot;psavert&quot;:            2.4,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 5758 
},
{
 &quot;date&quot;:          11108,
&quot;pce&quot;:         6712.1,
&quot;pop&quot;: 282156,
&quot;psavert&quot;:            2.5,
&quot;uempmed&quot;:            5.7,
&quot;unemploy&quot;: 5651 
},
{
 &quot;date&quot;:          11138,
&quot;pce&quot;:         6745.8,
&quot;pop&quot;: 282430,
&quot;psavert&quot;:            2.9,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 5747 
},
{
 &quot;date&quot;:          11169,
&quot;pce&quot;:         6766.7,
&quot;pop&quot;: 282706,
&quot;psavert&quot;:            2.8,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 5853 
},
{
 &quot;date&quot;:          11200,
&quot;pce&quot;:         6839.3,
&quot;pop&quot;: 282994,
&quot;psavert&quot;:            2.2,
&quot;uempmed&quot;:            5.2,
&quot;unemploy&quot;: 5625 
},
{
 &quot;date&quot;:          11230,
&quot;pce&quot;:         6846.2,
&quot;pop&quot;: 283271,
&quot;psavert&quot;:            2.3,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 5534 
},
{
 &quot;date&quot;:          11261,
&quot;pce&quot;:         6860.2,
&quot;pop&quot;: 283531,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 5639 
},
{
 &quot;date&quot;:          11291,
&quot;pce&quot;:         6908.5,
&quot;pop&quot;: 283782,
&quot;psavert&quot;:            1.5,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 5634 
},
{
 &quot;date&quot;:          11322,
&quot;pce&quot;:         6938.2,
&quot;pop&quot;: 284015,
&quot;psavert&quot;:            1.9,
&quot;uempmed&quot;:            5.8,
&quot;unemploy&quot;: 6023 
},
{
 &quot;date&quot;:          11353,
&quot;pce&quot;:         6969.2,
&quot;pop&quot;: 284240,
&quot;psavert&quot;:            1.7,
&quot;uempmed&quot;:            6.1,
&quot;unemploy&quot;: 6089 
},
{
 &quot;date&quot;:          11381,
&quot;pce&quot;:         6960.1,
&quot;pop&quot;: 284462,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:            6.6,
&quot;unemploy&quot;: 6141 
},
{
 &quot;date&quot;:          11412,
&quot;pce&quot;:         6978.5,
&quot;pop&quot;: 284701,
&quot;psavert&quot;:            1.6,
&quot;uempmed&quot;:            5.9,
&quot;unemploy&quot;: 6271 
},
{
 &quot;date&quot;:          11442,
&quot;pce&quot;:         7029.1,
&quot;pop&quot;: 284938,
&quot;psavert&quot;:              1,
&quot;uempmed&quot;:            6.3,
&quot;unemploy&quot;: 6226 
},
{
 &quot;date&quot;:          11473,
&quot;pce&quot;:           7045,
&quot;pop&quot;: 285198,
&quot;psavert&quot;:            1.1,
&quot;uempmed&quot;:              6,
&quot;unemploy&quot;: 6484 
},
{
 &quot;date&quot;:          11503,
&quot;pce&quot;:         7064.1,
&quot;pop&quot;: 285454,
&quot;psavert&quot;:            2.4,
&quot;uempmed&quot;:            6.8,
&quot;unemploy&quot;: 6583 
},
{
 &quot;date&quot;:          11534,
&quot;pce&quot;:         7098.6,
&quot;pop&quot;: 285730,
&quot;psavert&quot;:            3.7,
&quot;uempmed&quot;:            6.9,
&quot;unemploy&quot;: 7042 
},
{
 &quot;date&quot;:          11565,
&quot;pce&quot;:         7012.7,
&quot;pop&quot;: 286017,
&quot;psavert&quot;:            4.2,
&quot;uempmed&quot;:            7.2,
&quot;unemploy&quot;: 7142 
},
{
 &quot;date&quot;:          11595,
&quot;pce&quot;:           7222,
&quot;pop&quot;: 286287,
&quot;psavert&quot;:           -0.2,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 7694 
},
{
 &quot;date&quot;:          11626,
&quot;pce&quot;:         7177.2,
&quot;pop&quot;: 286545,
&quot;psavert&quot;:            0.7,
&quot;uempmed&quot;:            7.7,
&quot;unemploy&quot;: 8003 
},
{
 &quot;date&quot;:          11656,
&quot;pce&quot;:         7165.9,
&quot;pop&quot;: 286788,
&quot;psavert&quot;:            1.1,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 8258 
},
{
 &quot;date&quot;:          11687,
&quot;pce&quot;:         7196.5,
&quot;pop&quot;: 287021,
&quot;psavert&quot;:            2.9,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 8182 
},
{
 &quot;date&quot;:          11718,
&quot;pce&quot;:           7242,
&quot;pop&quot;: 287242,
&quot;psavert&quot;:            2.8,
&quot;uempmed&quot;:            8.3,
&quot;unemploy&quot;: 8215 
},
{
 &quot;date&quot;:          11746,
&quot;pce&quot;:         7252.3,
&quot;pop&quot;: 287453,
&quot;psavert&quot;:              3,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 8304 
},
{
 &quot;date&quot;:          11777,
&quot;pce&quot;:         7330.2,
&quot;pop&quot;: 287675,
&quot;psavert&quot;:            2.6,
&quot;uempmed&quot;:            8.9,
&quot;unemploy&quot;: 8599 
},
{
 &quot;date&quot;:          11807,
&quot;pce&quot;:         7296.2,
&quot;pop&quot;: 287916,
&quot;psavert&quot;:            3.1,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 8399 
},
{
 &quot;date&quot;:          11838,
&quot;pce&quot;:         7342.6,
&quot;pop&quot;: 288171,
&quot;psavert&quot;:            2.8,
&quot;uempmed&quot;:             11,
&quot;unemploy&quot;: 8393 
},
{
 &quot;date&quot;:          11868,
&quot;pce&quot;:         7396.4,
&quot;pop&quot;: 288427,
&quot;psavert&quot;:            1.9,
&quot;uempmed&quot;:            8.9,
&quot;unemploy&quot;: 8390 
},
{
 &quot;date&quot;:          11899,
&quot;pce&quot;:           7411,
&quot;pop&quot;: 288694,
&quot;psavert&quot;:            1.7,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 8304 
},
{
 &quot;date&quot;:          11930,
&quot;pce&quot;:         7382.3,
&quot;pop&quot;: 288965,
&quot;psavert&quot;:            2.2,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 8251 
},
{
 &quot;date&quot;:          11960,
&quot;pce&quot;:         7414.3,
&quot;pop&quot;: 289229,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:            9.6,
&quot;unemploy&quot;: 8307 
},
{
 &quot;date&quot;:          11991,
&quot;pce&quot;:         7443.6,
&quot;pop&quot;: 289477,
&quot;psavert&quot;:            1.8,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 8520 
},
{
 &quot;date&quot;:          12021,
&quot;pce&quot;:         7501.3,
&quot;pop&quot;: 289696,
&quot;psavert&quot;:            1.5,
&quot;uempmed&quot;:            9.6,
&quot;unemploy&quot;: 8640 
},
{
 &quot;date&quot;:          12052,
&quot;pce&quot;:         7522.1,
&quot;pop&quot;: 289913,
&quot;psavert&quot;:            1.8,
&quot;uempmed&quot;:            9.6,
&quot;unemploy&quot;: 8523 
},
{
 &quot;date&quot;:          12083,
&quot;pce&quot;:         7532.8,
&quot;pop&quot;: 290122,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 8622 
},
{
 &quot;date&quot;:          12111,
&quot;pce&quot;:         7589.5,
&quot;pop&quot;: 290331,
&quot;psavert&quot;:            1.7,
&quot;uempmed&quot;:            9.7,
&quot;unemploy&quot;: 8576 
},
{
 &quot;date&quot;:          12142,
&quot;pce&quot;:         7597.2,
&quot;pop&quot;: 290557,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:           10.2,
&quot;unemploy&quot;: 8833 
},
{
 &quot;date&quot;:          12172,
&quot;pce&quot;:         7619.2,
&quot;pop&quot;: 290791,
&quot;psavert&quot;:            2.3,
&quot;uempmed&quot;:            9.9,
&quot;unemploy&quot;: 8948 
},
{
 &quot;date&quot;:          12203,
&quot;pce&quot;:         7668.8,
&quot;pop&quot;: 291041,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:           11.5,
&quot;unemploy&quot;: 9254 
},
{
 &quot;date&quot;:          12233,
&quot;pce&quot;:         7723.3,
&quot;pop&quot;: 291289,
&quot;psavert&quot;:            2.8,
&quot;uempmed&quot;:           10.3,
&quot;unemploy&quot;: 9018 
},
{
 &quot;date&quot;:          12264,
&quot;pce&quot;:         7820.9,
&quot;pop&quot;: 291552,
&quot;psavert&quot;:            2.5,
&quot;uempmed&quot;:           10.1,
&quot;unemploy&quot;: 8894 
},
{
 &quot;date&quot;:          12295,
&quot;pce&quot;:         7803.7,
&quot;pop&quot;: 291811,
&quot;psavert&quot;:            1.7,
&quot;uempmed&quot;:           10.2,
&quot;unemploy&quot;: 8928 
},
{
 &quot;date&quot;:          12325,
&quot;pce&quot;:         7812.3,
&quot;pop&quot;: 292074,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:           10.4,
&quot;unemploy&quot;: 8731 
},
{
 &quot;date&quot;:          12356,
&quot;pce&quot;:         7868.5,
&quot;pop&quot;: 292318,
&quot;psavert&quot;:            2.2,
&quot;uempmed&quot;:           10.3,
&quot;unemploy&quot;: 8590 
},
{
 &quot;date&quot;:          12386,
&quot;pce&quot;:         7885.3,
&quot;pop&quot;: 292529,
&quot;psavert&quot;:            2.4,
&quot;uempmed&quot;:           10.4,
&quot;unemploy&quot;: 8338 
},
{
 &quot;date&quot;:          12417,
&quot;pce&quot;:         7977.7,
&quot;pop&quot;: 292723,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:           10.6,
&quot;unemploy&quot;: 8367 
},
{
 &quot;date&quot;:          12448,
&quot;pce&quot;:         8005.9,
&quot;pop&quot;: 292909,
&quot;psavert&quot;:            2.3,
&quot;uempmed&quot;:           10.2,
&quot;unemploy&quot;: 8171 
},
{
 &quot;date&quot;:          12477,
&quot;pce&quot;:         8070.5,
&quot;pop&quot;: 293112,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:           10.2,
&quot;unemploy&quot;: 8452 
},
{
 &quot;date&quot;:          12508,
&quot;pce&quot;:         8086.6,
&quot;pop&quot;: 293340,
&quot;psavert&quot;:            2.2,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 8155 
},
{
 &quot;date&quot;:          12538,
&quot;pce&quot;:         8196.5,
&quot;pop&quot;: 293569,
&quot;psavert&quot;:            1.5,
&quot;uempmed&quot;:            9.9,
&quot;unemploy&quot;: 8197 
},
{
 &quot;date&quot;:          12569,
&quot;pce&quot;:         8161.3,
&quot;pop&quot;: 293805,
&quot;psavert&quot;:            2.1,
&quot;uempmed&quot;:           10.9,
&quot;unemploy&quot;: 8259 
},
{
 &quot;date&quot;:          12599,
&quot;pce&quot;:         8235.3,
&quot;pop&quot;: 294056,
&quot;psavert&quot;:            1.7,
&quot;uempmed&quot;:            8.9,
&quot;unemploy&quot;: 8163 
},
{
 &quot;date&quot;:          12630,
&quot;pce&quot;:         8246.1,
&quot;pop&quot;: 294323,
&quot;psavert&quot;:              2,
&quot;uempmed&quot;:            9.3,
&quot;unemploy&quot;: 7993 
},
{
 &quot;date&quot;:          12661,
&quot;pce&quot;:         8313.7,
&quot;pop&quot;: 294587,
&quot;psavert&quot;:            1.2,
&quot;uempmed&quot;:            9.6,
&quot;unemploy&quot;: 7953 
},
{
 &quot;date&quot;:          12691,
&quot;pce&quot;:         8371.6,
&quot;pop&quot;: 294857,
&quot;psavert&quot;:            1.4,
&quot;uempmed&quot;:            9.5,
&quot;unemploy&quot;: 8052 
},
{
 &quot;date&quot;:          12722,
&quot;pce&quot;:         8410.8,
&quot;pop&quot;: 295105,
&quot;psavert&quot;:            1.2,
&quot;uempmed&quot;:            9.7,
&quot;unemploy&quot;: 7950 
},
{
 &quot;date&quot;:          12752,
&quot;pce&quot;:           8462,
&quot;pop&quot;: 295344,
&quot;psavert&quot;:            4.3,
&quot;uempmed&quot;:            9.4,
&quot;unemploy&quot;: 7997 
},
{
 &quot;date&quot;:          12783,
&quot;pce&quot;:         8469.4,
&quot;pop&quot;: 295576,
&quot;psavert&quot;:            0.9,
&quot;uempmed&quot;:            9.4,
&quot;unemploy&quot;: 7756 
},
{
 &quot;date&quot;:          12814,
&quot;pce&quot;:         8520.7,
&quot;pop&quot;: 295767,
&quot;psavert&quot;:            0.6,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 7966 
},
{
 &quot;date&quot;:          12842,
&quot;pce&quot;:           8569,
&quot;pop&quot;: 295975,
&quot;psavert&quot;:            0.2,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7683 
},
{
 &quot;date&quot;:          12873,
&quot;pce&quot;:         8654.4,
&quot;pop&quot;: 296209,
&quot;psavert&quot;:           -0.4,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7657 
},
{
 &quot;date&quot;:          12903,
&quot;pce&quot;:         8644.6,
&quot;pop&quot;: 296443,
&quot;psavert&quot;:           -0.1,
&quot;uempmed&quot;:            9.1,
&quot;unemploy&quot;: 7656 
},
{
 &quot;date&quot;:          12934,
&quot;pce&quot;:         8724.8,
&quot;pop&quot;: 296684,
&quot;psavert&quot;:           -0.5,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7507 
},
{
 &quot;date&quot;:          12964,
&quot;pce&quot;:         8833.9,
&quot;pop&quot;: 296940,
&quot;psavert&quot;:           -0.9,
&quot;uempmed&quot;:              9,
&quot;unemploy&quot;: 7464 
},
{
 &quot;date&quot;:          12995,
&quot;pce&quot;:         8825.5,
&quot;pop&quot;: 297207,
&quot;psavert&quot;:             -3,
&quot;uempmed&quot;:            9.2,
&quot;unemploy&quot;: 7360 
},
{
 &quot;date&quot;:          13026,
&quot;pce&quot;:         8882.5,
&quot;pop&quot;: 297471,
&quot;psavert&quot;:           -0.5,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7606 
},
{
 &quot;date&quot;:          13056,
&quot;pce&quot;:         8911.6,
&quot;pop&quot;: 297740,
&quot;psavert&quot;:           -0.3,
&quot;uempmed&quot;:            8.6,
&quot;unemploy&quot;: 7436 
},
{
 &quot;date&quot;:          13087,
&quot;pce&quot;:         8916.4,
&quot;pop&quot;: 297988,
&quot;psavert&quot;:           -0.3,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 7548 
},
{
 &quot;date&quot;:          13117,
&quot;pce&quot;:         8955.5,
&quot;pop&quot;: 298227,
&quot;psavert&quot;:           -0.3,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7331 
},
{
 &quot;date&quot;:          13148,
&quot;pce&quot;:         9034.4,
&quot;pop&quot;: 298458,
&quot;psavert&quot;:           -0.3,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7023 
},
{
 &quot;date&quot;:          13179,
&quot;pce&quot;:         9079.2,
&quot;pop&quot;: 298645,
&quot;psavert&quot;:           -0.3,
&quot;uempmed&quot;:            8.9,
&quot;unemploy&quot;: 7158 
},
{
 &quot;date&quot;:          13207,
&quot;pce&quot;:         9123.8,
&quot;pop&quot;: 298849,
&quot;psavert&quot;:           -0.4,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7009 
},
{
 &quot;date&quot;:          13238,
&quot;pce&quot;:         9175.2,
&quot;pop&quot;: 299079,
&quot;psavert&quot;:             -1,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7098 
},
{
 &quot;date&quot;:          13268,
&quot;pce&quot;:         9238.6,
&quot;pop&quot;: 299310,
&quot;psavert&quot;:           -1.6,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 7006 
},
{
 &quot;date&quot;:          13299,
&quot;pce&quot;:         9270.5,
&quot;pop&quot;: 299548,
&quot;psavert&quot;:           -1.5,
&quot;uempmed&quot;:            7.6,
&quot;unemploy&quot;: 6984 
},
{
 &quot;date&quot;:          13329,
&quot;pce&quot;:         9338.9,
&quot;pop&quot;: 299801,
&quot;psavert&quot;:           -1.7,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 7228 
},
{
 &quot;date&quot;:          13360,
&quot;pce&quot;:         9352.7,
&quot;pop&quot;: 300065,
&quot;psavert&quot;:           -1.5,
&quot;uempmed&quot;:            8.4,
&quot;unemploy&quot;: 7116 
},
{
 &quot;date&quot;:          13391,
&quot;pce&quot;:         9348.5,
&quot;pop&quot;: 300326,
&quot;psavert&quot;:             -1,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 6912 
},
{
 &quot;date&quot;:          13421,
&quot;pce&quot;:           9376,
&quot;pop&quot;: 300592,
&quot;psavert&quot;:           -0.8,
&quot;uempmed&quot;:              8,
&quot;unemploy&quot;: 6715 
},
{
 &quot;date&quot;:          13452,
&quot;pce&quot;:         9410.8,
&quot;pop&quot;: 300836,
&quot;psavert&quot;:           -0.9,
&quot;uempmed&quot;:            8.2,
&quot;unemploy&quot;: 6826 
},
{
 &quot;date&quot;:          13482,
&quot;pce&quot;:         9478.5,
&quot;pop&quot;: 301070,
&quot;psavert&quot;:           -1.1,
&quot;uempmed&quot;:            7.3,
&quot;unemploy&quot;: 6849 
},
{
 &quot;date&quot;:          13513,
&quot;pce&quot;:         9540.3,
&quot;pop&quot;: 301296,
&quot;psavert&quot;:           -0.9,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 7017 
},
{
 &quot;date&quot;:          13544,
&quot;pce&quot;:         9610.6,
&quot;pop&quot;: 301481,
&quot;psavert&quot;:             -1,
&quot;uempmed&quot;:            8.1,
&quot;unemploy&quot;: 6865 
},
{
 &quot;date&quot;:          13572,
&quot;pce&quot;:           9653,
&quot;pop&quot;: 301684,
&quot;psavert&quot;:           -0.7,
&quot;uempmed&quot;:            8.5,
&quot;unemploy&quot;: 6724 
},
{
 &quot;date&quot;:          13603,
&quot;pce&quot;:           9705,
&quot;pop&quot;: 301913,
&quot;psavert&quot;:           -1.3,
&quot;uempmed&quot;:            8.7,
&quot;unemploy&quot;: 6801 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt;
' scrolling='no' seamless class='rChart 
nvd3
 '
id='iframe-chart5e355533fb50'>
</iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>



<style>
  pre {padding: 0;}
  pre code {padding: 1rem;}
</style>
