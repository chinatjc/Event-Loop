## JS事件循环机制(Event Loop)

> 1. javascript是单线程的语言
> 2. Event Loop是javascript的执行机制

### 异步事件

+ 宏任务(macrotask)

	+ 整体代码 script

	+ setTimeout

	+ setInterval

+ 微任务(microtask)

	+ Promise.then catch finally

	+ MutationObserver

### Event Loop

执行顺序：执行一个宏任务 -> 执行所有的微任务 -> 渲染一次UI -> .....
[示例1](https://github.com/chinatjc/pageRender/tree/master/1)


![Event Loop](https://i.loli.net/2019/05/15/5cdc05fe6c3cf92991.png)

### 任务执行

异步任务：执行完异步任务的同步代码后，回调函数放入Event Table中注册，当指定的时机到了之后，回调函数会进入Event Queue队列中等待被执行。

![perform tasks](https://i.loli.net/2019/05/15/5cdc0643c648b71584.png)