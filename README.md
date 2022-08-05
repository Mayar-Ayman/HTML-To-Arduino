# HTML-To-Arduino
**In this repository i will explain how can send orders from HTML to Arduinou UNO.**\
*First need to use HTML, CSS, JavaScript, Arduino IDE and Arduino UNO.\
* HTML:\
All HTML documents must start with a <!DOCTYPE> declaration.
<!DOCTYPE html>\
<html lang="en" dir="ltr">\
<head>\
The charset attribute specifies the character encoding for the HTML document.
 <meta charset="utf-8">
 <title>speech to text in javascript</title>
<style>
    *{
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    -ms-box-sizing: border-box;
    box-sizing: border-box;
    }
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
    .container {
    text-align: center;
    }
    h1 {
    font-size: 30px;
    color: rgb(6, 4, 4);
    }
    textarea {
    width: 100%;
    height: 200px;
    border-radius: 10px;
    font-size: 20px;
    margin-bottom: 10px;
    }
    button,select{
    padding: 12px 20px ;
    background: rgb(198, 38, 38);
    border: 0px;
    border-radius: 10px;
    cursor: pointer;
    color: rgb(11, 88, 47);
    }

    button:hover,select:hover {
    background: rgb(197, 161, 230);
    color: white;
    }
</style>

 <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css">

</head>

<body>

 <div class="container">

 <h1 class="text-center mt-5">

 Speech to Text

 </h1>

 <div class="form-group">

 <textarea  id="textbox" rows="6" class="form-control"></textarea>

 </div>

 <div class="form-group">

 <button id="start-btn"  class="btn btn-danger btn-block" title="" >
    Start
 </button>
<button class = "btn btn-danger btn-block" onclick="onConnectUsb()" id="connect-usb">
    connect
</button>



 <p id="instructions">Press the Start button to start speech or connect button to connect to serial port</p>

 </div>

 </div>

 <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>

 <script src="script.js"></script>
<script src="arduino.js"></script>
<script>


</script>
</body>

</html>

 

