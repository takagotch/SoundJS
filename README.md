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
  .to()
  .to()
  .to()
  .to({ x: 100 ), 800, createjs.Ease.getPowInOut(2));
```

