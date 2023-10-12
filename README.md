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
        let resp = await gamerender.requestScreenshot("www.exampleupload.com", "files[]");
        console.log("resp", resp);
    }
    ```

- Normal method:

    ```js
    gamerender.requestScreenshot("www.exampleupload.com", "files[]").then((resp) => {
        console.log("resp", resp);
    })
    ```

#### Render GameView to a canvas element

Can be used for a lot of stuff: video calls, video record, live stream ...

- Start canvas render

    ```js
    const canvas = document.getElementById("videocall-canvas");

    gamerender.renderToTarget(canvas);
    ```

- Stop canvas render

    ```js
    gamerender.stop();
    ```