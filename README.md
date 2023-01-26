Payload-Loader
================

## What is this?

It is to make the operation of loading exploits on your ps4 from a WEB PAGE or host by DNS

## Requirements

Know the minimum in HTML,JS [Link](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics)

## Code in the button to start the Payload

```html run height=100
<button onclick=NamePayload()>Payload</button>
```
## JS code for the payload to work

```js run height=100
function toogle_payload(){
var req = new XMLHttpRequest();
req.responseType = "arraybuffer";
req.open("GET",PLfile,true);
req.send();
req.onreadystatechange=function(){
if (req.readyState == 4){
  var tmp0 = new Uint8Array(req.response.byteLength);
  tmp0.set(new Uint8Array(req.response), 0);
  var payload = new Uint32Array(tmp0);
  the_payload = payload;
  setTimeout(poc, 1500);
  }
};
```

## Payload operation with the button pressed

```js run height=100
function NamePayload(){
LoadedMSG="Nanme the Payload Loaded... Press OK Now !!!";
PLfile = "Location of the file to LOAD";
exec_type = "payload"; //Same name as the_payload
toogle_payload();
}
```




