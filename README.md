# HTML-To-Arduino
**In this repository i will explain how can send orders from HTML to Arduinou UNO.**\
First need to use HTML, CSS, JavaScript, Arduino IDE and Arduino UNO.\
**HTML:**\
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
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<script src="script.js"></script>
<script src="arduino.js"></script>
</html>
```

 At the top this is the basic formula  `<meta charset="utf-8">`  this command is specify the character encoding for the HTML document\
 Add The title of your page `<title>speech to text</title> ` .\
 * First, the body part we will add the interface design
 
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
 <textarea  id="textbox1" rows="6" class="form-control"></textarea>
 </div>
 ```
 ![Screenshot (347)](https://user-images.githubusercontent.com/108824980/183221678-3519b430-a63b-4a35-9157-67c02bf7e43b.png)
Now we put two buttons one to start and the other one to connection.

```
<div class="form-group">
 <button id="startbtn"  class="btn btn-danger btn-block" title="" >
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


* Second, the style part we will add the style design
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
            
            
 ![image](https://user-images.githubusercontent.com/108824980/183247700-81322dc2-757b-4127-a016-3a10e0c38ff7.png).
  
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
    

 ![image](https://user-images.githubusercontent.com/108824980/183247747-ae09d318-3871-45ed-a695-cac06177c53a.png)
   
   This command shows a color when you click on one of the buttons
  `button:hover,select:hover {
    background: rgb(216, 210, 211);
    color: rgb(23, 21, 21);
    }
     .`
   ![image](https://user-images.githubusercontent.com/108824980/183247776-7217e7a0-d7f5-4bbf-9d17-6138221a57bb.png)
   
   **JavaScript files:** 
   * We must create two JavaScript files: \
   1.the first one for convert speech to text.\
   2.the second file for connect Arduio to the HTML.
  
  * Convert speach to text JavaSript file.
  
  ```
  <script>
    startbtn.addEventListener('click', function(){
    var speech = true;
    window.SpeechRecognition = window.webkitSpeechRecognition;
   const recognition =new SpeechRecognition();
   recognition.interimResults = true;
   
   recognition.addEventListener('result', e=>{
   const transcript = Array.from(e.results)
   .map(result => result[0])
   .map(result => result.transcript)
   
   textbox1.innerHTML = transcript;
   })
   recognition.lang="ar";
   
   if(speech == true){
   recognition.start();
   }
})
</script>
```
  
The `recognition.lang="ar";` use for Arabic language.

![image](https://user-images.githubusercontent.com/108824980/183250685-c010f853-b05e-4ca1-b0c6-e1bb3715b138.png)

* To send commands from HTML to Arduio UNO.
* 
```
let isConnectted = false;
    let port;
    let writer;
    var target_id;
    const enc = new TextEncoder()
    
  async function onConnectUsb() {
    try {
      const requestOptions = {
        // Filter on devices with the Arduino USB vendor ID.
        filters: [{ usbVendorId: 0x2341 }],
      };

      // Request an Arduino from the user.
      port = await navigator.serial.requestPort(requestOptions);
      await port.open({ baudRate: 115200 });
      writer = port.writable.getWriter();
      isConnectted = true;
    } catch (e) {
      console.log("err", e);
    }
  }
  ```
TextEncoder takes a stream of code points as input and emits a stream of bytes `TextEncoder().`\
The `navigator.serial.requestPort()` function takes an optional object literal that defines filters. Those are used to match any serial device connected over USB with a mandatory USB vendor` (usbVendorId)` and optional USB product identifiers `(usbProductId)`.\

```
 async function onConnectUsb() {
    try {
      const requestOptions = {
        // Filter on devices with the Arduino USB vendor ID.
        filters: [{ usbVendorId: 0x2341 }],
      };
      
Calling `requestPort()` prompts the user to select a device and returns a `SerialPort` object. Once you have a `SerialPort` object, calling `port.open()` with the desired baud rate will open the serial port. The `baudRate` dictionary member specifies how fast data is sent over a serial line./

```
 port = await navigator.serial.requestPort(requestOptions);
      await port.open({ baudRate: 115200 });
      writer = port.writable.getWriter();
      isConnectted = true;
 ```


  ![image](https://user-images.githubusercontent.com/108824980/183251721-ad642624-c065-4d2c-ae6d-d44b17d744c9.png)

  
