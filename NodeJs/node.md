##相关学习资料
很重要，写在开头:  
[https://cnodejs.org/getstart](https://cnodejs.org/getstart)

##HTTP模块
监听2015端口，返回hello

```js
    var http = require("http");
    http
        .createServer(function(req, res) {
            res.writeHead(200, {
                "Content-Type": "text/plain"
            });
            res.write("hello");
            res.end();
        })
        .listen(2015)
```

##模块使用
```js
    //page.js
    var http = require("http");

    function start() {
        http
            .createServer(function(req, res) {
                res.writeHead(200, {
                    "Content-Type": "text/plain"
                });
                res.write("hello");
                res.end();
            })
            .listen(2015);
    }
    exports.start = start;
```

```js
    //index.js
    var page = require("./page"); //可直接写page，但是必须位于node_modules里
    page.start();
```
exports.start = start;

##EVENT模块

```js
    var EventEmitter = require("events").EventEmitter;
    var life = new EventEmitter();
    //addEventListener
    life.on("change", function(who) {
        console.log(who + "change");
    });
    life.on("change", function(who) {
        console.log(who + "change2");
    });
    life.emit("change", "file");
```
