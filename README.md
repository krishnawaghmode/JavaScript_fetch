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
## file Read fetch() Examples
```javascript
 fetch("my_file/readme.txt")
        .then((response) => {
			console.log(response);
		});      

 //output

 //promise return 
 //PromiseState->fulfilled
 //promiseResult->  "This file content read"  



   fetch("my_file/readme.txt")
      .then((response) => {
			return response.text();
		}).then((data)=>{
			console.log(data);
		});   

      // Shortcut 1
      fetch("my_file/readme.txt")
     .then((response)=>response.text())
     .then((data)=>document.write(data));

          // Shortcut 2
       fetch("my_file/readme.txt")
      .then(res => res.text())
      .then(data => document.write(data));
```
