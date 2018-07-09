---
---
<body onload="callGoogleScript();">
<script>
    // Make an AJAX call to Google Script
  function callGoogleScript() {
    var url = "https://script.google.com/macros/s/AKfycbyd3OPH7qwydqI9BGWn2oSU5uWGjwFwrg4I_nOU90alk7MwjIrQ/exec?callback=ctrlq&id="+ urlPara("id");
    
    var request = jQuery.ajax({
      crossDomain: true,
      url: url + encodeURIComponent(id),
      method: "GET",
      dataType: "jsonp"
    });

  }
  // print the returned data
  function ctrlq(e) {
  var div = document.getElementById('main_content');
        div.innerHTML = e.result1;
  }
  
 //get url parameters
 function urlPara(p){
 var url_string = window.location.href;
var url = new URL(url_string);
return url.searchParams.get(p);
}

</script>
<!-- MAIN CONTENT -->
    <div id="main_content_wrap" class="outer">
      <section id="main_content" class="row">
        <p>Loading....</p>
     </section>
    </div>
</body>
