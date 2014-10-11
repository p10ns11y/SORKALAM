var lookup = document.getElementById('word').value;
    	 
var url = "https://glosbe.com/gapi/translate?from=eng&dest=ta&format=json&phrase=" + lookup + "&pretty=true";
 
console.log('Looking up: ' + url);

var xhr = new XMLHttpRequest();
xhr.open("GET",url,true);
console.log(xhr);
 
xhr.onreadystatechange = function() {
  				if (xhr.readyState == 4) {
   // JSON.parse does not evaluate the attacker's scripts.
 				var resp = JSON.parse(xhr.responseText);
  				}
 }
 xhr.send();