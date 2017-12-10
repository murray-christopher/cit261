<h1>AJAX</h1>
<h3>AJAX = Asynchronous JavaScript And XML.</h3>
*in our case we will use it with JSON.<br/><br/>

What does it do?
 - Update a web page without reloading the page
 - Request data from a server - after the page has loaded
 - Receive data from a server - after the page has loaded
 - Send data to a server - in the background

<h3>Overview</h3>
<image src="https://www.w3schools.com/xml/ajax.gif"></image>

<h3>Steps</h3>

1. An event occurs in a web page (the page is loaded, a button is clicked)
2. An XMLHttpRequest object is created by JavaScript
3. The XMLHttpRequest object sends a request to a web server
4. The server processes the request
5. The server sends a response back to the web page
6. The response is read by JavaScript
7. Proper action (like page update) is performed by JavaScript

<h3>Handling a JSON file</h3>

function loadJSON() {
  var xhttp = new XMLHttpRequest(); //this allows us to listen in to the state changes of http
  xhttp.onreadystatechange = function() { //this function runs when the ready state changes
    if (this.readyState == 4 && this.status == 200) { //this checks to see that the status from the server is good
      var students = JSON.parse(this.responseText); //this grabs the file ans puts it in a json object
      document.getElementById("demo").innerHTML = students[1].name; //accesses the first students name and displays it
    }
  };
  xhttp.open("GET", "StudentList.json", true); //GET tells the browser to get the file name studentlist
  xhttp.send();
}


<h3>What the Json file looks like</h3>

StudentList.json

[{
  "id": 1,
  "first_name": "Cully",
  "last_name": "Hort",
  "email": "chort0@bloglovin.com"
}, {
  "id": 2,
  "first_name": "Starr",
  "last_name": "Braniff",
  "email": "sbraniff1@weebly.com"
}, {
  "id": 3,
  "first_name": "Aryn",
  "last_name": "Solley",
  "email": "asolley2@twitter.com"
}, {
  "id": 4,
  "first_name": "Raimundo",
  "last_name": "Huyge",
  "email": "rhuyge3@sina.com.cn"
}, {
  "id": 5,
  "first_name": "Adore",
  "last_name": "Berre",
  "email": "aberre4@whitehouse.gov"
}]
