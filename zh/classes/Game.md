## `Game` 类型

继承于 [`EventTarget`](EventTarget.md)


模块: [cc](../modules/cc.md)




cc.game 是 Game 的实例，用来驱动整个游戏。

### 索引

##### 属性（properties）

  - [`EVENT_HIDE`](#eventhide) `String` Event triggered when game hide to background.
Please note that this event is not 100% guaranteed to be fired.
  - [`EVENT_SHOW`](#eventshow) `String` Event triggered when game back to foreground
Please note that this event is not 100% guaranteed to be fired.
  - [`EVENT_GAME_INITED`](#eventgameinited) `String` Event triggered after game inited, at this point all engine objects and game scripts are loaded
  - [`EVENT_RENDERER_INITED`](#eventrendererinited) `String` Event triggered after renderer inited, at this point you will be able to use the render context
  - [`CONFIG_KEY`](#configkey) `Object` Key of config
  - [`frame`](#frame) `Object` 游戏画布的外框，cc.container 的父类。
  - [`container`](#container) `HTMLDivElement` 游戏画布的容器。
  - [`canvas`](#canvas) `HTMLCanvasElement` 游戏的画布。
  - [`config`](#config) `Object` 当前的游戏配置，包括：                                                                  <br/>
1. debugMode（debug 模式，但是在浏览器中这个选项会被忽略）                                <br/>
     "debugMode" 各种设置选项的意义。                                                   <br/>
         0 - 没有消息被打印出来。                                                       <br/>
         1 - cc.error，cc.assert，cc.warn，cc.log 将打印在 console 中。                  <br/>
         2 - cc.error，cc.assert，cc.warn 将打印在 console 中。                          <br/>
         3 - cc.error，cc.assert 将打印在 console 中。                                   <br/>
         4 - cc.error，cc.assert，cc.warn，cc.log 将打印在 canvas 中（仅适用于 web 端）。 <br/>
         5 - cc.error，cc.assert，cc.warn 将打印在 canvas 中（仅适用于 web 端）。         <br/>
         6 - cc.error，cc.assert 将打印在 canvas 中（仅适用于 web 端）。                  <br/>
2. showFPS（显示 FPS）                                                            <br/>
     当 showFPS 为 true 的时候界面的左下角将显示 fps 的信息，否则被隐藏。              <br/>
3. exposeClassName                                                           <br/>
     暴露类名让 Chrome DevTools 可以识别，如果开启会稍稍降低类的创建过程的性能，但对对象构造没有影响。 <br/>
4. frameRate (帧率)                                                              <br/>
     “frameRate” 设置想要的帧率你的游戏，但真正的FPS取决于你的游戏实现和运行环境。      <br/>
5. id                                                                            <br/>
     "gameCanvas" Web 页面上的 Canvas Element ID，仅适用于 web 端。                         <br/>
6. renderMode（渲染模式）                                                         <br/>
     “renderMode” 设置渲染器类型，仅适用于 web 端：                              <br/>
         0 - 通过引擎自动选择。                                                     <br/>
         1 - 强制使用 canvas 渲染。
         2 - 强制使用 WebGL 渲染，但是在部分 Android 浏览器中这个选项会被忽略。     <br/>
7. scenes                                                                         <br/>
     “scenes” 当前包中可用场景。                                                   <br/>
<br/>
注意：请不要直接修改这个对象，它不会有任何效果。



##### 方法

  - [`onStart`](#onstart) 当引擎完成启动后的回调函数。
  - [`setFrameRate`](#setframerate) 设置游戏帧率。
  - [`step`](#step) 执行一帧游戏循环。
  - [`pause`](#pause) 暂停游戏主循环。包含：游戏逻辑，渲染，事件处理，背景音乐和所有音效。这点和只暂停游戏逻辑的 cc.director.pause 不同。
  - [`resume`](#resume) 恢复游戏主循环。包含：游戏逻辑，渲染，事件处理，背景音乐和所有音效。
  - [`isPaused`](#ispaused) 判断游戏是否暂停。
  - [`restart`](#restart) 重新开始游戏
  - [`end`](#end) 退出游戏
  - [`prepare`](#prepare) 准备引擎，请不要直接调用这个函数。
  - [`run`](#run) 运行游戏，并且指定引擎配置和 onStart 的回调。
  - [`addPersistRootNode`](#addpersistrootnode) 声明常驻根节点，该节点不会被在场景切换中被销毁。<br/>
目标节点必须位于为层级的根节点，否则无效。
  - [`removePersistRootNode`](#removepersistrootnode) 取消常驻根节点。
  - [`isPersistRootNode`](#ispersistrootnode) 检查节点是否是常驻根节点。
  - [`on`](#on) 注册事件目标的特定事件类型回调。
  - [`off`](#off) 删除之前用同类型，回调，目标或 useCapture 注册的事件监听器，如果只传递 type，将会删除 type 类型的所有事件监听器。
  - [`targetOff`](#targetoff) 在当前 EventTarget 上删除指定目标（target 参数）注册的所有事件监听器。
这个函数无法删除当前 EventTarget 的所有事件监听器，也无法删除 target 参数所注册的所有事件监听器。
这个函数只能删除 target 参数在当前 EventTarget 上注册的所有事件监听器。
  - [`once`](#once) 注册事件目标的特定事件类型回调，回调会在第一时间被触发后删除自身。
  - [`dispatchEvent`](#dispatchevent) 分发事件到事件流中。
  - [`emit`](#emit) 该对象直接发送事件， 这种方法不会对事件传播到任何其他对象。



### Details


#### 属性（properties）


##### EVENT_HIDE

> Event triggered when game hide to background.
Please note that this event is not 100% guaranteed to be fired.

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:46](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L46) |

##### 示例

```js
cc.game.on(cc.game.EVENT_HIDE, function () {
    cc.audioEngine.pauseMusic();
    cc.audioEngine.pauseAllEffects();
});
```


##### EVENT_SHOW

> Event triggered when game back to foreground
Please note that this event is not 100% guaranteed to be fired.

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:59](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L59) |



##### EVENT_GAME_INITED

> Event triggered after game inited, at this point all engine objects and game scripts are loaded

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:67](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L67) |



##### EVENT_RENDERER_INITED

> Event triggered after renderer inited, at this point you will be able to use the render context

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:74](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L74) |



##### CONFIG_KEY

> Key of config

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:88](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L88) |



##### frame

> 游戏画布的外框，cc.container 的父类。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:126](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L126) |



##### container

> 游戏画布的容器。

| meta | description |
|------|-------------|
| 类型 | HTMLDivElement |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:133](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L133) |



##### canvas

> 游戏的画布。

| meta | description |
|------|-------------|
| 类型 | HTMLCanvasElement |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:140](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L140) |



##### config

> 当前的游戏配置，包括：                                                                  <br/>
1. debugMode（debug 模式，但是在浏览器中这个选项会被忽略）                                <br/>
     "debugMode" 各种设置选项的意义。                                                   <br/>
         0 - 没有消息被打印出来。                                                       <br/>
         1 - cc.error，cc.assert，cc.warn，cc.log 将打印在 console 中。                  <br/>
         2 - cc.error，cc.assert，cc.warn 将打印在 console 中。                          <br/>
         3 - cc.error，cc.assert 将打印在 console 中。                                   <br/>
         4 - cc.error，cc.assert，cc.warn，cc.log 将打印在 canvas 中（仅适用于 web 端）。 <br/>
         5 - cc.error，cc.assert，cc.warn 将打印在 canvas 中（仅适用于 web 端）。         <br/>
         6 - cc.error，cc.assert 将打印在 canvas 中（仅适用于 web 端）。                  <br/>
2. showFPS（显示 FPS）                                                            <br/>
     当 showFPS 为 true 的时候界面的左下角将显示 fps 的信息，否则被隐藏。              <br/>
3. exposeClassName                                                           <br/>
     暴露类名让 Chrome DevTools 可以识别，如果开启会稍稍降低类的创建过程的性能，但对对象构造没有影响。 <br/>
4. frameRate (帧率)                                                              <br/>
     “frameRate” 设置想要的帧率你的游戏，但真正的FPS取决于你的游戏实现和运行环境。      <br/>
5. id                                                                            <br/>
     "gameCanvas" Web 页面上的 Canvas Element ID，仅适用于 web 端。                         <br/>
6. renderMode（渲染模式）                                                         <br/>
     “renderMode” 设置渲染器类型，仅适用于 web 端：                              <br/>
         0 - 通过引擎自动选择。                                                     <br/>
         1 - 强制使用 canvas 渲染。
         2 - 强制使用 WebGL 渲染，但是在部分 Android 浏览器中这个选项会被忽略。     <br/>
7. scenes                                                                         <br/>
     “scenes” 当前包中可用场景。                                                   <br/>
<br/>
注意：请不要直接修改这个对象，它不会有任何效果。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:148](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L148) |






<!-- Method Block -->
#### 方法


##### onStart

当引擎完成启动后的回调函数。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:210](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L210) |



##### setFrameRate

设置游戏帧率。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:221](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L221) |

###### 参数列表
- frameRate <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### step

执行一帧游戏循环。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:238](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L238) |



##### pause

暂停游戏主循环。包含：游戏逻辑，渲染，事件处理，背景音乐和所有音效。这点和只暂停游戏逻辑的 cc.director.pause 不同。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:247](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L247) |



##### resume

恢复游戏主循环。包含：游戏逻辑，渲染，事件处理，背景音乐和所有音效。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:267](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L267) |



##### isPaused

判断游戏是否暂停。

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:284](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L284) |



##### restart

重新开始游戏

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:294](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L294) |



##### end

退出游戏

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:321](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L321) |



##### prepare

准备引擎，请不要直接调用这个函数。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:331](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L331) |

###### 参数列表
- cb <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> 


##### run

运行游戏，并且指定引擎配置和 onStart 的回调。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:431](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L431) |

###### 参数列表
- config <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> Pass configuration object or onStart function
- onStart <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> function to be executed after game initialized


##### addPersistRootNode

声明常驻根节点，该节点不会被在场景切换中被销毁。<br/>
目标节点必须位于为层级的根节点，否则无效。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:455](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L455) |

###### 参数列表
- node <a href="../classes/Node.html" class="crosslink">Node</a> The node to be made persistent


##### removePersistRootNode

取消常驻根节点。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:491](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L491) |

###### 参数列表
- node <a href="../classes/Node.html" class="crosslink">Node</a> The node to be removed from persistent node list


##### isPersistRootNode

检查节点是否是常驻根节点。

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js:507](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/CCGame.js#L507) |

###### 参数列表
- node <a href="../classes/Node.html" class="crosslink">Node</a> The node to be checked


##### on

注册事件目标的特定事件类型回调。

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:217](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L217) |

###### 参数列表
- type <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> A string representing the event type to listen for.
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> The callback that will be invoked when the event is dispatched.
                             The callback is ignored if it is a duplicate (the callbacks are unique).
	- event <a href="../classes/Event.html" class="crosslink">Event</a> event
- target <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The target (this object) to invoke the callback, can be null
- useCapture <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> When set to true, the capture argument prevents callback
                             from being invoked when the event's eventPhase attribute value is BUBBLING_PHASE.
                             When false, callback will NOT be invoked when event's eventPhase attribute value is CAPTURING_PHASE.
                             Either way, callback will be invoked when event's eventPhase attribute value is AT_TARGET.

##### 示例

```js
node.on(cc.Node.EventType.TOUCH_END, function (event) {
    cc.log("this is callback");
}, node);
```

##### off

删除之前用同类型，回调，目标或 useCapture 注册的事件监听器，如果只传递 type，将会删除 type 类型的所有事件监听器。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:274](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L274) |

###### 参数列表
- type <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> A string representing the event type being removed.
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> The callback to remove.
- target <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The target (this object) to invoke the callback, if it's not given, only callback without target will be removed
- useCapture <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Specifies whether the callback being removed was registered as a capturing callback or not.
                             If not specified, useCapture defaults to false. If a callback was registered twice,
                             one with capture and one without, each must be removed separately. Removal of a capturing callback
                             does not affect a non-capturing version of the same listener, and vice versa.

##### 示例

```js
// register touchEnd eventListener
var touchEnd = node.on(cc.Node.EventType.TOUCH_END, function (event) {
    cc.log("this is callback");
}, node);
// remove touch end event listener
node.off(cc.Node.EventType.TOUCH_END, touchEnd, node);
// remove all touch end event listeners
node.off(cc.Node.EventType.TOUCH_END);
```

##### targetOff

在当前 EventTarget 上删除指定目标（target 参数）注册的所有事件监听器。
这个函数无法删除当前 EventTarget 的所有事件监听器，也无法删除 target 参数所注册的所有事件监听器。
这个函数只能删除 target 参数在当前 EventTarget 上注册的所有事件监听器。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:329](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L329) |

###### 参数列表
- target <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The target to be searched for all related listeners


##### once

注册事件目标的特定事件类型回调，回调会在第一时间被触发后删除自身。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:351](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L351) |

###### 参数列表
- type <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> A string representing the event type to listen for.
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> The callback that will be invoked when the event is dispatched.
                             The callback is ignored if it is a duplicate (the callbacks are unique).
	- event <a href="../classes/Event.html" class="crosslink">Event</a> event
- target <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The target (this object) to invoke the callback, can be null
- useCapture <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> When set to true, the capture argument prevents callback
                             from being invoked when the event's eventPhase attribute value is BUBBLING_PHASE.
                             When false, callback will NOT be invoked when event's eventPhase attribute value is CAPTURING_PHASE.
                             Either way, callback will be invoked when event's eventPhase attribute value is AT_TARGET.

##### 示例

```js
node.once(cc.Node.EventType.TOUCH_END, function (event) {
    cc.log("this is callback");
}, node);
```

##### dispatchEvent

分发事件到事件流中。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:396](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L396) |

###### 参数列表
- event <a href="../classes/Event.html" class="crosslink">Event</a> The Event object that is dispatched into the event flow


##### emit

该对象直接发送事件， 这种方法不会对事件传播到任何其他对象。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js:410](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/event/event-target.js#L410) |

###### 参数列表
- message <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> the message to send
- detail Any whatever argument the message needs



