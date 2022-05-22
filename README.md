
# Tower Builder Game

a tower building game using ES6 and Canvas.

this version is ready to use with webxdc as well as for usage in a browser (just open index.html locally),
based on <https://github.com/iamkun/tower_game>

<img src="https://user-images.githubusercontent.com/17680888/47480922-93a20c00-d864-11e8-8f7c-6d1d60184730.gif"/>


## Game Rule

The following are the default game rule:

- In every game player starts with 3 hp. Every time a Tower block is dropped player is deduct 1 hp; game ends when hp is depleted.

- Player is rewarded with 25 point for every successful stacked blocks(Success). If a block is stacked pefectly (Perfect) on top of the previous one, then player
rewarded with 50 points instead. Consecutive Perfects awards additional 25 points.
Note: Each Success or Perfect constitutes a floor.

For example, the first Perfect awards 50 point. The second consecutive Perfect awards 75 points. 
The third consecutive Perfect awards 100 points.  etc.

<img width="350" src="https://user-images.githubusercontent.com/17680888/47473105-d9021180-d843-11e8-8c19-b6b78d86cbdf.png" />


## Customizing

Open `http://localhost:8082` in a web browser.
To customize image and sound resource files directly replace the corresponding file under `assets` directory.
To customize game rules modify the `option` object in `index.html`.

Use following table of `option` constants to complete customization of game rules.

**Note: all constants are optionally included**

| Option | Type | Description |
|---------|--------|-------------|
| width          | number | Width of game interface |
| height         | number | Height of game interface |
| canvasId       | string | DOM ID in Canvas |
| soundOn        | boolean | If sound is on |
| successScore   | number | Points awarded for success |
| perfectScore   | number | Additional points awarded for perfect |
| <a href="#hookspeed">hookSpeed</a> | function | Speed of hook's movement |
| <a href="#hookangle">hookAngle</a> | function | Angle of hook |
| <a href="#landblockspeed">landBlockSpeed</a> | function | Speed of block sway |
| <a href="#setgamescore">setGameScore</a> | function | hook for current score |
| <a href="#setgamesuccess">setGameSuccess</a> | function | hook for number of current succesful game |
| <a href="#setgamefailed">setGameFailed</a> | function | hook for number of current failed game |

#### hookSpeed
Speed of hook's movement
This function takes in two parameters, currentFloor and currentScore, and returns a speed value.
```
function(currentFloor, currentScore) {
  return number
}
```

#### hookAngle
Angle of hook
This function takes in two parameters, currentFloor and currentScore, and returns a angle value.
```
function(currentFloor, currentScore) {
  return number
}
```

#### landBlockSpeed
Speed of block sway
This function takes in two parameters, currentFloor and currentScore, and returns a speed value.
```
function(currentFloor, currentScore) {
  return number
}
```

#### setGameScore
hook for current score
This function takes in one parameters, score, and sets currentScore to score.
```
function(score) {
  // your logic
}
```

#### setGameSuccess
hook for number of current succesful game
This function takes in one parameters, score, and sets GameSuccess to successCount.
```
function(successCount) {
  // your logic
}
```

#### setGameFailed
hook for number of current failed game
This function takes in one parameters, score, and sets GameFailed to failedCount.
```
function(failedCount) {
  // your logic
}
```

## License

MIT license.

Music CC-BY-SA 3.0 Matthew Pablo, Caketown, <https://opengameart.org/content/caketown-cuteplayful>
