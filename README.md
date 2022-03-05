# JavaScript Fetch API Explained By Examples
>fetch() method works on Live Server
## syntax
```javascript

  fetch(file/URL).then();


  fetch(file/URL).then(function(response) {
		   	return response.data;//text(),json()
		});



       fetch(file/URL)
         .then(function(response) {
          return response.data;//text(),json()
       }).then(function(response) {
   
			   console.log(response);
      
		  }).catch(function(error){
           console.log(error);
		 });
```
