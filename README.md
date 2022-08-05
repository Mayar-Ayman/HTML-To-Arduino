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
 **On the body part we will add the interface design**
 
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








