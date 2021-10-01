# Jquery-Plugin-Virtual-Numpad-PinCode
jquery plugin to create virtual numpad for pin auth


# Usage
```html
<center><div id="pinpad"/></center>
```
# run this javascript
var pinform = pinMeBB("pinpad",{
  "limit":5,
  "minChar":5,
});

# callbacks
```javascript
$(document).ready(function () {Cancel changes
    pinform.addEventListener('onEnter', e => {
    when pres enter
       var pin = e.detail.password();
        apex.event.trigger("#pinpad",'done_pin',pin);
    });
    pinform.addEventListener('onMaxChar', e => {
    //when reach limit
        console.log("MAXED");
    });
    pinform.addEventListener('onEmpty', e => {
      //when some pin still missing (default min Char is the same as limit)
        apex.event.trigger("#pinpad",'empty_pin');
    });  
});
```
