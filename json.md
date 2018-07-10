---
---
<body onload="callGoogleScript();">
<script>
    // Make an AJAX call to Google Script
    var id= urlPara("id");
  function callGoogleScript() {
    var url = "https://script.google.com/macros/s/AKfycbyd3OPH7qwydqI9BGWn2oSU5uWGjwFwrg4I_nOU90alk7MwjIrQ/exec?callback=ctrlq&id="+id ;
    
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
       console.log(e.result1);
       div.innerHTML = e.result2;
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
