---
---
<html>
  <head>
    <title>hello</title>
  </head>
<body onload="callGoogleScript();">
<script>
    // Make an AJAX call to Google Script
  function callGoogleScript() {
    var url = "https://script.google.com/macros/s/AKfycbyd3OPH7qwydqI9BGWn2oSU5uWGjwFwrg4I_nOU90alk7MwjIrQ/exec?callback=ctrlq&name="+ urlPara("id");
    
    var request = jQuery.ajax({
      crossDomain: true,
      url: url + encodeURIComponent(name),
      method: "GET",
      dataType: "jsonp"
    });

  }
  // print the returned data
  function ctrlq(e) {
    console.log(e.result)
  }
  
 //get url parameters
 function urlPara(p){
 var url_string = window.location.href;
var url = new URL(url_string);
return url.searchParams.get(p);
}

</script>
</body>
</html>
