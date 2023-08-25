# m3u8-to-mp4

This module helps you convert an M3U8 file to an MP4 file easily using ffmpeg/node.js

## Installation

This module can be installed via npm. You will also need to install ffmpeg for this module to work:

```sh
$ sudo apt install ffmpeg
$ npm install --save m3u8-to-mp4
```

## Usage

```js
var m3u8ToMp4 = require("m3u8-to-mp4");
var converter = new m3u8ToMp4();
```

### Functions

#### converter.setInputFile(filename)

- **filename:** M3U8 file path. You can use remote URL

#### converter.setOutputFile(filename)

- **filename:** Output file path. Has to be local :)

#### converter.start()

```js
var m3u8ToMp4 = require("m3u8-to-mp4");
var converter = new m3u8ToMp4();

(async function() {
  await converter
    .setInputFile("https://<URL_OF_THE_WEBSITE>/<PATH_TO_THE_M3U8_FILE>")
    .setOutputFile("dummy.mp4")
    .start();

  console.log("File converted");
})();
```

tracking progress

```js
var m3u8ToMp4 = require("m3u8-to-mp4");
var converter = new m3u8ToMp4();

async function download_hls(url, video_path, dob) {
    return new Promise(async (resolve, reject) => {
      global.currentEvent = eventx;

  await converter
.setInputFile(url)
.setOutputFile(video_path+'.mp4')
.start({
        onProgress: progress => { if (typeof progress.percent !== 'undefined' && progress.percent !== null){
         console.log('Converting to mp4...'+progress.percent.toFixed(2)+'%');
        } else {
  console.log('Converting to mp4...0.01%');
          
        }  },
        onEnd: () => {console.log('Finished Download!')}
      })
.then(async() => {
  //console.log("File converted");
  eventx.sender.send('finishedDownload', 'done downloading.');
addTojson(dob, function(x) {resolve(true)});

});
});
}
```
