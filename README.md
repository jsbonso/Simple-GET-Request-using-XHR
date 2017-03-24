# Simple-GET-Request-using-XHR



This is just a simple example on how to do a HTTP GET Request using plain old javascript, via XHR, 
without any external library or any other framework. 


With all of the tons of new javascript frameworks out there in the market, the newbies are now getting confused and becoming overly dependent 
with the freshly 
baked javascript stuff, to the point that they can't even do a simple HTTP call without the use of a javascript framework. 


Sadly, even the experienced IT Professionals also falls into this trap, and missing the essential vanilla javascript skill they need to 
fully comprehend 
the tools and frameworks they are using. 

Hence, it's good to have this simple example as a refresher. 



# Demo
See it in action here: 
https://jsbonso.github.io/Simple-GET-Request-using-XHR/


# Running Locally

To run this example on your machine, just open the index.html file and click the GET Data button. That's simple!


You can change the targetUrl variable with any REST API or any webservice that you have.

```javascript
<script>
function getData() {
  var xhttp = new XMLHttpRequest();
  var targetUrl = 'https://angelfire-af88c.firebaseio.com/students.json';
  
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById('demo').innerHTML = this.responseText;
    } else if (this.status) {
      document.getElementById('demo').innerHTML = 'Can not access: ' + targetUrl 
	+ ' <br /> Response: ' + this.status + ' ' + this.responseText;
    } else {
      document.getElementById('demo').innerHTML = 'Loading...';
    }
  };
  
  xhttp.open('GET', targetUrl, true);
  xhttp.send();
}
</script>
```

Wanna be fancy? Then you can run this using any HTTP Server, like http-server from NPM: https://www.npmjs.com/package/http-server

	npm install http-server -g 
	http-server
