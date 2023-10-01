# Jquery-Plugin-Virtual-Numpad-PinCode

jquery plugin to create virtual numpad for pin auth

# Usage

```html
<html>
  <script
    src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js"
    integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  ></script>
  <link rel="stylesheet" href="pinMeBB.css" />
  <script src="pinMeBB.js"></script>
  <script>
    $(document).ready(function () {
      var pinform = pinMeBB("pinpad", { limit: 5, minChar: 5 });
      pinform.addEventListener("onEnter", (e) => {
        //    when pres enter
        var pin = e.detail.password();
        alert("Enter Pressed! \n Pin : " + pin);
      });
      pinform.addEventListener("onMaxChar", (e) => {
        //when max length reached
        var pin = e.detail.password();
        alert("MAXED Char Reached! \n Pin : " + pin);
      });
      pinform.addEventListener("onEmpty", (e) => {
        //when some pin still missing (default min Char is the same as limit)
        alert("Pin Cant be Empty!");
      });
    });
  </script>
  <body>
    <div id="pinpad"></div>
  </body>
</html>
```

# run this javascript

var pinform = pinMeBB("pinpad",{
"limit":5,
"minChar":5,
});

# callbacks

```javascript
var pinform = pinMeBB("pinpad", { limit: 5, minChar: 5 });
pinform.addEventListener("onEnter", (e) => {
  //    when pres enter
  var pin = e.detail.password();
  alert("Enter Pressed! \n Pin : " + pin);
});
pinform.addEventListener("onMaxChar", (e) => {
  //when max length reached
  var pin = e.detail.password();
  alert("MAXED Char Reached! \n Pin : " + pin);
});
pinform.addEventListener("onEmpty", (e) => {
  //when some pin still missing (default min Char is the same as limit)
  alert("Pin Cant be Empty!");
});
```
