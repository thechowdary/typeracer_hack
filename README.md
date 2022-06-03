# typeracer_hack
This repository is for educational purpose on how to hack typeracer.com from your browser's console window.

**Hacking steps:**
1. Start a race with your friends on typeracer.com
2. Press F12 on keyboard 
3. Goto console window
4. Copy and paste our code in the console section but don't hit enter until the game begins.

```
function autoPressKeyboard(el, keyCode, type)
{
    var eventObj = document.createEventObject ?
        document.createEventObject() : document.createEvent("Events");
  
    if(eventObj.initEvent){
      eventObj.initEvent(type, true, true);
    }
  
    eventObj.keyCode = keyCode;
    eventObj.which = keyCode;
    
    el.dispatchEvent ? el.dispatchEvent(eventObj) : el.fireEvent("onkeydown", eventObj); 
  
} 
$=$$
fullcontent=''
for(i=0; i < $('table > tbody > tr:nth-child(2) > td > table > tbody > tr:nth-child(1) > td > table > tbody > tr:nth-child(1) > td > div > div > span').length; i++) {
	fullcontent+=$('table > tbody > tr:nth-child(2) > td > table > tbody > tr:nth-child(1) > td > table > tbody > tr:nth-child(1) > td > div > div > span')[i].textContent;
}
letters = fullcontent.split('');
j = 0;

function a () {
	if (j == letters.length ) return; //use *letters.length - 1* here to let you type the last letter to decide your speed on your own.
	txtInput = $('table > tbody > tr:nth-child(2) > td > table > tbody > tr:nth-child(2) > td > input')[0]
	txtInput.focus()
	txtInput.value += letters[j++];
	autoPressKeyboard(txtInput, txtInput.value.charCodeAt(0), "keydown")
	txtInput.click()
	autoPressKeyboard(txtInput, txtInput.value.charCodeAt(0), "keypress")
	autoPressKeyboard(txtInput, txtInput.value.charCodeAt(0), "keyup")
	setTimeout(a, 250 * Math.random()) //trying to keep your speed under 100 to not get caught.
}
a();
```

5. You can hit enter once game started after the countdown. Then relax :) 
