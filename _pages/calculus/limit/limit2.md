---
title: Limit
smartdown: true
lesson: 'limit'
header: 'none'
ogimage: /assets/images/calculus/limits.jpg
---


# :::: success
# --partialborder
Success!
$$ 
\lim_{x \to 3} \frac{x^2 + x -12}{x-3} = 7
$$
[Continue](/pages/limit3-1)
# --partialborder
# ::::

# :::: note1 
# --partialborder
You can drag the blue slider to get close to $x=1$, but you can get super close and still not reach it by using the [closer](:=reduce=true) button multiple times.
# --partialborder
# ::::
### More Limits

#### --outlinebox outer1

#### --outlinebox left1


#### --outlinebox


#### --outlinebox right1
Here's another limit.
$$ 
\lim_{x \to 3} \frac{x^2 + x -12}{x-3}
$$

1. Go [closer](:=reduce=true) to $x=3$.  
2. Go [all the way](:=all=true) to $x=3$.
[NOTE:](::note1/tooltip,transparent)

The expression is undefined
The limit as $x$ gets close to $3$ is [](:?s1). 

#### --outlinebox
#### --outlinebox

 

```javascript /autoplay

const outer = document.getElementById('outer1');
const left = document.getElementById('left1');
const right = document.getElementById('right1');

outer.classList.remove('decoration-outlinebox');
left.classList.remove('decoration-outlinebox');
right.classList.remove('decoration-outlinebox');

outer.classList.add('outer-multi-col');
left.classList.add('playable-2-col');
right.classList.add('text-2-col');


//smartdown.import=https://cdnjs.cloudflare.com/ajax/libs/jsxgraph/0.99.7/jsxgraphcore.js

smartdown.importCssUrl('https://cdnjs.cloudflare.com/ajax/libs/jsxgraph/0.99.7/jsxgraph.css');

// import the calc library
//smartdown.import=/assets/libs/calc.js


left.innerHTML = `<div id='box' class='jxgbox' style='height:600px'>`;

let xlow = -2;
let xhigh = 6;
let ylow = -2;
let yhigh = 10;

let th = new BlueTheme();

let workspace = new Workspace('box', [xlow,yhigh,xhigh,ylow], {xlabel:'', ylabel:''});
let F = new ProblemFunction(
	function(x) { return x + 4; }, 
	'', 3.5, [xlow,xhigh], []);
let F_id = workspace.addFunction(F);

let limit = new ApproachLimit(workspace.board, F.f, 3, undefined);
limit.glider.moveTo([2,0]);



/////////////////////////////////////////////////////////////////////////////////////////

// Event handling

this.div.onmousedown = function(e) { 
  
};


let heightPercent = 0.7;

this.sizeChanged = function() {
  workspace.board.resizeContainer(left.offsetWidth, window.innerHeight * heightPercent);
};


this.sizeChanged();


workspace.board.on('update', function() {
	limit.onUpdate();
  workspace.onUpdate();              // hook up workspace update functions
});


smartdown.setVariable('reduce', false);
smartdown.setVariable('all', false);

this.dependOn = ['reduce', 'all'];  
this.depend = function() {
  
	if (env.reduce == true) {
		smartdown.setVariable('reduce', false);
		limit.reduceDelta();		
	}

	if (env.all == true) {
		smartdown.setVariable('all', false);
		limit.eliminateDelta();
	}


};

outer.classList.add('outer-multi-col');
left.classList.add('playable-2-col');
right.classList.add('text-2-col');


```


```javascript /autoplay

smartdown.setVariable('s1','');
this.dependOn = ['s1'];  
this.depend = function() {
  
	if (env.s1 == '7') {
		smartdown.showDisclosure('success','','center,transparent,draggable,outline,closeable,shadow');
	}

};
```
