# ezAlert
A small VanillaJS plugin to create alerts similar to jQuery+Bootstrap.  

Main function is initAlert, explained perfectly in the code. Copy pasted comment:

**initAlert(target, content, dismissible = 'button', allowSpec = true, extraClasses = '', closeClass = '')**  

     The target can be an element ID, or the element itself.
     It will first check whether the target is a string, then whether an id like that exists.
     If the target is not a string, it will check whether it is an object.

     Content can be any content for the alert. Only if allowSpec is true can the content contain HTML (and most other characters)

     If dismissible is not false, alert will be dismissible.
     If the value is 'button', will create a button to dismiss (default).
     If the value is 'click', will be dismissible on click.

     If allowSpec is false, content will only be allowed to contain word characters,',','.','?','!', and '.

     extraClasses will add more classes to this specific alert.

     closeClass will specify the name of the button that closes the class (default 'close')
    

**Example**:  
The following is a function used to generate alerts that work with the default Bootstrap alert CSS:  

    function alertLog(str, type = 'info', allowSpec = true, closeClass = ''){
        if(document.alertHandler === undefined)
            document.alertHandler = new ezAlert('alert');
        document.alertHandler.initAlert(document.body,str,'button',allowSpec,'alert-'+type,closeClass);
    }
