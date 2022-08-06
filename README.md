# HTML-To-Arduino
**In this repository i will explain how can send orders from HTML to Arduinou UNO.**\
First need to use HTML, CSS, JavaScript, Arduino IDE and Arduino UNO.
* HTML:\
All HTML documents must start with a `<!DOCTYPE>` declaration

```
<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
<meta charset="utf-8">
<style>


</style>
<title>speech to text</title>


</head>
<body>


</body>
<script src="script.js"></script>
<script src="arduino.js"></script>
</html>
```

 At the top this is the basic formula  `<meta charset="utf-8">`  this command is specify the character encoding for the HTML document\
 Add The title of your page `<title>speech to text</title> ` .\
 **First, the body part we will add the interface design**
 
 ```
 <div class="container">
 <h1 class="text-center mt-5">
 Speech to Text
 </h1>
 ```
Here we have entered text
![Screenshot (346)](https://user-images.githubusercontent.com/108824980/183220935-03b92617-c2c3-4a40-9325-f88fc9d207fd.png)
Add textbox to appear spoken word
```
<div class="form-group">
 <textarea  id="textbox" rows="6" class="form-control"></textarea>
 </div>
 ```
 ![Screenshot (347)](https://user-images.githubusercontent.com/108824980/183221678-3519b430-a63b-4a35-9157-67c02bf7e43b.png)
Now we put two buttons one to start and the other one to connection.

```
<div class="form-group">
 <button id="start-btn"  class="btn btn-danger btn-block" title="" >
   Start
 </button>
<button class = "btn btn-danger btn-block" onclick="onConnectUsb()" id="connect-usb">
  connection
</button>
```
![image](https://user-images.githubusercontent.com/108824980/183247546-1ec91e2b-59f7-4b41-959d-85c317550495.png)

put text under the two buttons
`<p id="instructions">Press the Start button to start speech or connect button to connect to serial port</p>`
![image](https://user-images.githubusercontent.com/108824980/183247643-298f127d-0cc6-4043-9cdf-8ff18458a08e.png)


**Second, the style part we will add the style design**\
body style

```
  body{
    background:linear-gradient(to right , rgb(125, 172, 196), rgb(227, 229, 245) );
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    color: #000;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 16px;
    margin: 0;
            }
 ```
            
            
  ![image](https://user-images.githubusercontent.com/108824980/183223189-a6e40452-d71a-42b4-a3dc-a8a52a4757d4.png).
  
    .container {
    text-align: center;
    }
    textarea {
    width: 100%;
    height: 200px;
    border-radius: 50px;
    font-size: 20px;
    margin-bottom: 10px;
    }
    button,select{
    padding: 14px 70px ;
    background: rgb(234, 231, 231);
    border: 0px;
    border-radius: 10px;
    cursor: pointer;
    color: rgb(0, 0, 0);
    }
    button:hover,select:hover {
    background: rgb(216, 210, 211);
    color: rgb(23, 21, 21);
    }

   ![image](https://user-images.githubusercontent.com/108824980/183225108-ed25368d-3ce1-42d2-b5f2-a1f21a69ce0d.png)
   
   This code shows a color when you click on one of the buttons
  `button:hover,select:hover {
    background: rgb(216, 210, 211);
    color: rgb(23, 21, 21);
    }
     .`
    
    
   ![image](https://user-images.githubusercontent.com/108824980/183226943-1b45e894-c8a3-4f43-be8a-e98a4c5cad74.png)

  
