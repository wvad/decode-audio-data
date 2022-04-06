# decodeAudioData
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Usage
```js
const { decodeAudioData } = require("decode-audio-data");
decodeAudioData(
  fs.readFileSync("music.mp3")
);
// return: Promise<AudioBuffer>
```
```js
const { decodeAudioDataStream } = require("decode-audio-data");
decodeAudioDataStream(
  fs.createReadStream("music.mp3")
);
// return: ReadableStream<Buffer>
```

## decodeAudioData(input\[, options\])
### Parameters
#### `input` [&lt;Buffer&gt;](https://nodejs.org/api/buffer.html#buffer_class_buffer) | [&lt;Uint8Array&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) | [&lt;Readable&gt;](https://nodejs.org/api/stream.html#stream_class_stream_readable)   
A Buffer containing the audio data to be decoded
#### `options` (optional) [&lt;Object&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)  
Options for decoding
#### `options.numberOfChannels` [&lt;number&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type) 
An integer representing the number of channels this buffer should have. The default value is 2
#### `options.sampleRate` [&lt;number&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)
The sample rate of the linear audio data in sample-frames per second. The default value is 48000
### Return value
#### `decodedData` &lt;[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[AudioBuffer](https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer)&gt;&gt;
A Promise object that fulfills with the decoded aduio data

## decodeAudioDataStream(stream\[, options\])
### Parameters
#### `stream` [&lt;Readable&gt;](https://nodejs.org/api/stream.html#stream_class_stream_readable)
A Readable stream containing the audio data to be decoded
#### `options` (optional)  [&lt;Object&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
Options for decoding
#### `options.numberOfChannels` [&lt;number&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)
An integer representing the number of channels this buffer should have. The default value is 1
#### `options.sampleRate` [&lt;number&gt;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type)
The sample rate of the linear audio data in sample-frames per second. The default value is 48000
### Return value
#### `decodedData` &lt;[Readable](https://nodejs.org/api/stream.html#stream_class_stream_readable)&lt;[Buffer](https://nodejs.org/api/buffer.html#buffer_class_buffer)&gt;&gt;
A Readable stream containing decoded audio data
