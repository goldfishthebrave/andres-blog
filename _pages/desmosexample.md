---
title: 'Notes for Andre because I Love Him'
smartdown: true
header: 'none'
---




### Desmos

It's easy to add a desmos page.  

```javascript /autoplay

// first I make a javascript app and put it on autoplay.  
// You can replace to word autoplay with playable to see what that does.

// this sets the width and height of the playable
const myDiv = this.div;        
myDiv.style.width = '100%';
myDiv.style.height = '100%';
myDiv.style.margin = 'auto';


// I've set the width to be 100 percent of the playable and the height to be 600 pixels
// you just need to paste in the web address of your desmos page as the value for src.  
// Note that all these values are strings so they need to be in quotes.

myDiv.innerHTML = `<iframe src="https://www.desmos.com/calculator/rqvx3utuef" width="100%" height="600px" style="border: 1px solid #ccc" frameborder=0></iframe>`;

```



