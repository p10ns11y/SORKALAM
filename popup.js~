/**
 * Wait before the DOM has been loaded before initializing the Ubuntu UI layer*/
 
$( document ).ready(function () {    

    // Wire all the simple logic
    $("#lookup").click(function(){ 
       var lookup = document.getElementById('word').value;
    	 
		 var url = "https://glosbe.com/gapi/translate?from=eng&dest=ta&format=json&phrase=" + lookup + "&callback=result&pretty=true";
		 
		 		 
		 $.ajax({
			 type: 'GET',
			 url: url,
			 success: result,
			 dataType: 'jsonp',
			 contentType: "application/json"
	    });
        
    });
    console.log('AJAX send');

});



function result( data ){
    console.log('AJAX success');

    var resEl = document.getElementById('res');
    var res = '<ul><header>வெவ்வேறு சொற்கள் </header></ul>';


    for( var i = 0; i < data.tuc.length; i++ ) {
        if ( data.tuc[i].phrase ) {
            console.log('phrase');

                if( data.tuc[i].phrase.language === 'ta'){
                	  
                    res += '<li>' + data.tuc[i].phrase.text + '</li>';
                }
            }
    }

    for( var idx1 = 0; idx1 < data.tuc.length; idx1++ ) {
        if ( data.tuc[idx1].meanings ) {
            console.log('meanings');
            for (var idx2 = 0; idx2 < data.tuc[idx1].meanings.length; idx2++) {
                console.log( data.tuc[idx1].meanings[idx2].text );
                if( data.tuc[idx1].meanings[idx2].language === 'ta'){
                    res += '<li>' + data.tuc[idx1].meanings[idx2].text + '</li>';
                }
            }
        }


    }
    resEl.innerHTML = res + '</ul>';
}