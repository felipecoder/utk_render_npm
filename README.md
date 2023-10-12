# utk-render-npm
utk-render-npm is an npm library adapted from the original [utk-render](https://github.com/utkuali/utk_render) code

## Installation

```
npm  i utk-render
```

## Usage

```js
import { GameRender } from 'utk-render'
const gamerender = new GameRender()
```

## Handling Screenshot Uploads

To handle screenshot upload requests you can use this php code: https://github.com/melihozkara/fivem-php-img-uploader

### Functions

#### Request Screenshot

Takes a screenshot and uploads it to the defined url

- Async method:

    ```js
    async function takeScreenshot() {
        let resp = await GameRender.requestScreenshot("www.exampleupload.com", "files[]");
        console.log("resp", resp);
    }
    ```

- Normal method:

    ```js
    GameRender.requestScreenshot("www.exampleupload.com", "files[]").then((resp) => {
        console.log("resp", resp);
    })
    ```

#### Render GameView to a canvas element

Can be used for a lot of stuff: video calls, video record, live stream ...

- Start canvas render

    ```js
    const canvas = document.getElementById("videocall-canvas");

    GameRender.renderToTarget(canvas);
    ```

- Stop canvas render

    ```js
    GameRender.stop();
    ```

## Important Note

Realtime render was made for my own phone therefore, render width and height ratio is fixed for 250px 575px which is 10 / 23 however, you can change this by some simple edits:

- script.js line:37 and line:97

    ```js
    // this width is 10 / 23 which is 250 to 575
    const width = Math.floor(window.innerHeight * 10 / 23);

    // 3rd parameter is left offset for the camera, setting it to 0 means most left side of the game, setting it to window.innerWidth / 2 means half of the game
    cameraRTT.setViewOffset(window.innerWidth, window.innerHeight, window.innerWidth / 3.5, 0, width, window.innerHeight);
    ```