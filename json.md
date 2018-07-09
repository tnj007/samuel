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
    
    var url = "https://script.google.com/macros/s/123/exec?callback=ctrlq&name=";
    var name = "Amit Agarwal"

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
</script>
</body>
</html>
