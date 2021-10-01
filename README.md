# Jquery-Plugin-Virtual-Numpad-PinCode
jquery plugin to create virtual numpad for pin auth

/*prepare space for the numpad
<center>
<div id="pinpad"/>  <!-- this is where we put the numpad -->
</center>
*/


// run this javascript
pinform = pinMeBB("pinpad",{
"limit":5,
"minChar":5,
});

$(document).ready(function () {
    pinform.addEventListener('onEnter', e => {
    //when pres enter
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
