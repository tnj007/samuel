---
layout: card
---
<body onload="callGoogleScript();">
<script>
    // Make an AJAX call to Google Script
    var id= urlPara("id");
    
  function callGoogleScript() {
    var url = "https://script.google.com/macros/s/AKfycbyd3OPH7qwydqI9BGWn2oSU5uWGjwFwrg4I_nOU90alk7MwjIrQ/exec?callback=loadData&id=" ;

var request = jQuery.ajax({
      crossDomain: true,
      url: url + encodeURIComponent(id),
      method: "GET",
      dataType: "jsonp"
    });

  }
  // print the returned data
  function loadData(e) {
  var div = document.getElementById('main_content');
       div.innerHTML = e.result1;
             console.log(e.result2);

  }
  
 //get url parameters
 function urlPara(p){
 var url_string = window.location.href;
var url = new URL(url_string);
return url.searchParams.get(p);
}

</script>
</body>
