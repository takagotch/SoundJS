### SoundJs
---
https://github.com/CreateJS/SoundJS

```js
createjs.Sound.on("fileload", handleLoadComplete);
createjs.Sound.alternateExtensions = ["mp3"];
createjs.Sound.registerSound({src:"path/to/sound.ogg", id:"sound"});
function handleLoadComplete(event){
  createjs.Sound.play("sound");
}
```

```
<body onload="init();">
  <canvas id="demoCanvas" width="500" height="300"></canvas>
</body>

<button onclick="loadImage();" class="load-image">Load Image</button>
```

```js
funciton init(){
}

var stage = new createjs.State("demoCanvas");

var circle = new createjs.Shape();
circle.graphics.begiFill("DeepSkyBlue").drawCircle(0, 0, 50);
circle.x = 100;
circle.y = 100;
stage.addChild(circle);

stage.update();

createjs.Tween.get(circle, { loop: true })
  .to({ x: 400 }, 1000, createjs.Ease.getPowInOut(4))
  .to({ alpha: 0, y: 175 }, 500, creates.Ease.getPowInOut(2))
  .to({ alpha: 0, y: 225 }, 100)
  .to({ alpha: 1, y: 200 }, 500, createjs.Ease.getPowInOut(2))
  .to({ x: 100 ), 800, createjs.Ease.getPowInOut(2));

createjs.Ticker.setFPS(60);
createjs.Ticker.addEventListener("tick", stage);

var soundID = "Thunder";

function loadSound(){
  createjs.Sound.registerSound("assets/thunder.mp3", soundID);
}

function playSound(){
  createjs.Sound.play(soundID);
}

function loadImage(){
  var preload = new createjs.LoadQueue();
  preload.addEventListener("fileload", handleFileComplete);
  preload.loadFile("assets/preloadjs-bg-center.png");
}

function handleFileComplete(event){
  document.body.appendChild(event.result);
}
```

