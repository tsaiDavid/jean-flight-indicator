[logo-compass]: img/compass.preview.png
[logo-speed]: img/speed.preview.png
[logo-altitude]: img/altitude.preview.png

[logo-horizon]: img/horizon.preview.png
[logo-vertical-speed]: img/vertical-speed.preview.png 
[logo-altitude]: img/altitude.svg 

[logo-stick]: img/stick.preview.png
[logo-pedal]: img/pedal.preview.png
[logo-collective]: img/collective.preview.png

[logo-coming-soon]: img/coming_soon.preview.png

## Description

Provides functionality for displaying flight parameters.

## Installation

`npm install jean-flight-indicator --save --legacy-bundling`
  
## Preview

- Visit an  [implemented example](https://je-an.github.io/jean-flight-indicator/example/index.html)

Standard
---

|     Compass     |    Speed      |      Altitude    |
|:----------:|:----------:|:----------:|
|     ![compass indicator][logo-compass]    |     ![Speed indicator][logo-speed]      |   ![Altitude indicator][logo-coming-soon]       |
|     Displays aircraft heading    |     Displays aircraft speed    |  Displays aircraft altitude    |

---

|     Horizon     |   Vertical Speed      |      Turn    |
|:----------:|:----------:|:----------:|
|     ![compass indicator][logo-coming-soon]     |     ![Speed indicator][logo-coming-soon]      |   ![Altitude indicator][logo-coming-soon]       |
|    Displays aircraft pitch and roll    |     Displays aircraft vertical speed     |  Displays aircraft turn       |    

Helicopter specific
---
 
|     Stick     |    Pedal      |      Collective    |
|:----------:|:----------:|:----------:|
|     ![Stick indicator][logo-stick]     |     ![Pedal indicator][logo-pedal]      |   ![Collective indicator][logo-collective]       |
|     Displays helicopter stick position     |     Displays helicopter pedal position    |  Displays helicopter collective hand gear position       |

## Code Example
- Use it as browser variable

```js
// Set basic options for all flight indicators
FlightIndicator.setOptions({
        assets: "../img/" // path where the svgs are located
});

// Create all indicator and pass the id of the html element 
// which shall be used as container
 var speed = new FlightIndicator.Speed({
        containerId: "speed-container"
});
var compass = new FlightIndicator.Compass({
    containerId: "compass-container"
});
var stick = new FlightIndicator.Stick({
    containerId: "stick-container"
});
var pedal = new FlightIndicator.Pedal({
    containerId: "pedal-container"
});
var collective = new FlightIndicator.Collective({
    containerId: "collective-container"
});

// Update methods. 
speed.update(/* number within range from 0 to 160 */);
compass.update(/* number within range from 360 to -360 */);
stick.update(
    /* number within range from 1 to -1 */, 
    /* number within range from 1 to -1 */
);
pedal.update(
    /* number within range from 1 to 0 */, 
    /* number within range from 1 to 0 */
);
collective.update(/* number within range from 60 to 0 */);
```

- Use it with require.js

```js
require(["path/to/FlightIndicator"], function(FlightIndicator){
    // Work with FlightIndicator
});
```

## Debugging

- Host `example/index.html` and display it in your browser

## Support
Supports AMD eco system. If there is no loader, FlightIndicator is registered as a browser variable.

## License

MIT

