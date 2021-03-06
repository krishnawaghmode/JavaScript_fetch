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
## Quotes.json file Read fetch() Examples
```javascript
 /*   Quotes.json

       [
          {
	          quote:"try try but don't cry",
	          author:"life"
          },
          {
              quote:"Growth is Life",
	          author:"life"
	       }
       ]
  */
  fetch("Quotes.json")
  .then(response) => response.json()
  .then((data) => {

   for (var x in data) {
     console.log(`${data[x].quote} <br>`);
     console.log(`${data[x].author} <br>`);
  }

});         
.catch((error) => document.write("Can't fetch data")); 
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
## Live server URL with fetch()
```javascript
//syntax
 fetch("https:jsonplaceholder.typicode.com/users")
.then(response) => response.json()
.then((data) => console.log(data));         
.catch((error) => document.write("Can't fetch data"); 

//code
 fetch("https:jsonplaceholder.typicode.com/users")
.then(response) => response.json()
.then((data) => {

    for (var x in data) {
      console.log(`${data[x].name} <br>`);
      console.log(`${data[x].address.city} <br>`);
    }
 });         
.catch((error) => document.write("Can't fetch data");
```
## HTML form CRUD insert fetch()
```javascript
                   /*
                      fetch("https:jsonplaceholder.typicode.com/posts",{
	                     method:"POST",  //"PUT","DELETE","GET"
	                     body:data,    //formData/json
                       headers:{
	                    'Content-type':'application/json'
                         },

                      }).then(response) => response.json()
                      .then((json) => console.log(json));         
                  */
		  
      <form id="myForm">
           Title <input type="text" id="title"><br><br>
           Body <input type="text" id="body"><br><br>
           User Id <input type="text" id="userId"><br><br>
           <input type="submit" id="saveform">
      </form>
      
    
    document.getElementById("saveform").addEventListener("click",function(e){
	     e.preventDefault();


     fetch("https:jsonplaceholder.typicode.com/posts",{
	   method:"POST", 
	   body:new FormData(document.getElement("myform")),    
           headers:{
	            'Content-type':'application/x-www-form-urlencoded',
           },

      })
      .then((response) => response.json())
      .then((json) => console.log(json));   
     });
```	 
	 
```
