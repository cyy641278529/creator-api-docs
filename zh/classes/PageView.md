## `PageView` 类型

继承于 [`ScrollView`](ScrollView.md)


模块: [cc](../modules/cc.md)




页面视图组件

### 索引

##### 属性（properties）

  - [`sizeMode`](#sizemode) `PageView.SizeMode` 页面视图中每个页面大小类型
  - [`direction`](#direction) `PageView.Direction` 页面视图滚动类型
  - [`scrollThreshold`](#scrollthreshold) `Number` 滚动临界值，默认单位百分比，当拖拽超出该数值时，松开会自动滚动下一页，小于时则还原。
  - [`autoPageTurningThreshold`](#autopageturningthreshold) `Number` 快速滑动翻页临界值。
当用户快速滑动时，会根据滑动开始和结束的距离与时间计算出一个速度值，
该值与此临界值相比较，如果大于临界值，则进行自动翻页。
  - [`pageTurningEventTiming`](#pageturningeventtiming) `Number` 设置 PageView PageTurning 事件的发送时机。
  - [`indicator`](#indicator) `PageViewIndicator` 页面视图指示器组件
  - [`pageTurningSpeed`](#pageturningspeed) `Number` 每个页面翻页时所需时间。单位：秒
  - [`pageEvents`](#pageevents) `Component.EventHandler[]` 滚动视图的事件回调函数
  - [`content`](#content) `Node` 可滚动展示内容的节点。
  - [`horizontal`](#horizontal) `Boolean` 是否开启水平滚动。
  - [`vertical`](#vertical) `Boolean` 是否开启垂直滚动。
  - [`inertia`](#inertia) `Boolean` 是否开启滚动惯性。
  - [`brake`](#brake) `Number` 开启惯性后，在用户停止触摸后滚动多快停止，0表示永不停止，1表示立刻停止。
  - [`elastic`](#elastic) `Boolean` 是否允许滚动内容超过边界，并在停止触摸后回弹。
  - [`bounceDuration`](#bounceduration) `Number` 回弹持续的时间，0 表示将立即反弹。
  - [`horizontalScrollBar`](#horizontalscrollbar) `Scrollbar` 水平滚动的 ScrollBar。
  - [`verticalScrollBar`](#verticalscrollbar) `Scrollbar` 垂直滚动的 ScrollBar。
  - [`scrollEvents`](#scrollevents) `Component.EventHandler[]` 滚动视图的事件回调函数
  - [`cancelInnerEvents`](#cancelinnerevents) `Boolean` 如果这个属性被设置为 true，那么滚动行为会取消子节点上注册的触摸事件，默认被设置为 true。
注意，子节点上的 touchstart 事件仍然会触发，触点移动距离非常短的情况下 touchmove 和 touchend 也不会受影响。
  - [`__eventTargets`](#eventtargets) `Array` Register all related EventTargets,
all event callbacks will be removed in _onPreDestroy
  - [`node`](#node) `Node` 该组件被附加到的节点。组件总会附加到一个节点。
  - [`uuid`](#uuid) `String` 组件的 uuid，用于编辑器。
  - [`_enabled`](#enabled) `Boolean` 
  - [`enabled`](#enabled) `Boolean` 表示该组件自身是否启用。
  - [`enabledInHierarchy`](#enabledinhierarchy) `Boolean` 表示该组件是否被启用并且所在的节点也处于激活状态。
  - [`_isOnLoadCalled`](#isonloadcalled) `Number` 返回一个值用来判断 onLoad 是否被调用过，不等于 0 时调用过，等于 0 时未调用。
  - [`_name`](#name) `String` 
  - [`_objFlags`](#objflags) `Number` 
  - [`name`](#name) `String` 该对象的名称。
  - [`isValid`](#isvalid) `Boolean` 表示该对象是否可用（被销毁后将不可用）。



##### 方法

  - [`getCurrentPageIndex`](#getcurrentpageindex) 返回当前页面索引
  - [`setCurrentPageIndex`](#setcurrentpageindex) 设置当前页面索引
  - [`getPages`](#getpages) 返回视图中的所有页面
  - [`addPage`](#addpage) 在当前页面视图的尾部插入一个新视图
  - [`insertPage`](#insertpage) 将页面插入指定位置中
  - [`removePage`](#removepage) 移除指定页面
  - [`removePageAtIndex`](#removepageatindex) 移除指定下标的页面
  - [`removeAllPages`](#removeallpages) 移除所有页面
  - [`scrollToPage`](#scrolltopage) 滚动到指定页面
  - [`scrollToBottom`](#scrolltobottom) 视图内容将在规定时间内滚动到视图底部。
  - [`scrollToTop`](#scrolltotop) 视图内容将在规定时间内滚动到视图顶部。
  - [`scrollToLeft`](#scrolltoleft) 视图内容将在规定时间内滚动到视图左边。
  - [`scrollToRight`](#scrolltoright) 视图内容将在规定时间内滚动到视图右边。
  - [`scrollToTopLeft`](#scrolltotopleft) 视图内容将在规定时间内滚动到视图左上角。
  - [`scrollToTopRight`](#scrolltotopright) 视图内容将在规定时间内滚动到视图右上角。
  - [`scrollToBottomLeft`](#scrolltobottomleft) 视图内容将在规定时间内滚动到视图左下角。
  - [`scrollToBottomRight`](#scrolltobottomright) 视图内容将在规定时间内滚动到视图右下角。
  - [`scrollToOffset`](#scrolltooffset) 视图内容在规定时间内将滚动到 ScrollView 相对左上角原点的偏移位置, 如果 timeInSecond参数不传，则立即滚动到指定偏移位置。
  - [`getScrollOffset`](#getscrolloffset) 获取滚动视图相对于左上角原点的当前滚动偏移
  - [`getMaxScrollOffset`](#getmaxscrolloffset) 获取滚动视图最大可以滚动的偏移量
  - [`scrollToPercentHorizontal`](#scrolltopercenthorizontal) 视图内容在规定时间内将滚动到 ScrollView 水平方向的百分比位置上。
  - [`scrollTo`](#scrollto) 视图内容在规定时间内进行垂直方向和水平方向的滚动，并且滚动到指定百分比位置上。
  - [`scrollToPercentVertical`](#scrolltopercentvertical) 视图内容在规定时间内滚动到 ScrollView 垂直方向的百分比位置上。
  - [`stopAutoScroll`](#stopautoscroll) 停止自动滚动, 调用此 API 可以让 Scrollview 立即停止滚动
  - [`setContentPosition`](#setcontentposition) 设置当前视图内容的坐标点。
  - [`getContentPosition`](#getcontentposition) 获取当前视图内容的坐标点。
  - [`isScrolling`](#isscrolling) 用户是否在拖拽当前滚动视图
  - [`isAutoScrolling`](#isautoscrolling) 当前滚动视图是否在惯性滚动
  - [`update`](#update) 如果该组件启用，则每帧调用 update。
  - [`lateUpdate`](#lateupdate) 如果该组件启用，则每帧调用 LateUpdate。
  - [`__preload`](#preload) `__preload` is called before every onLoad.
It is used to initialize the builtin components internally,
to avoid checking whether onLoad is called before every public method calls.
This method should be removed if script priority is supported.
  - [`onLoad`](#onload) 当附加到一个激活的节点上或者其节点第一次激活时候调用。onLoad 总是会在任何 start 方法调用前执行，这能用于安排脚本的初始化顺序。
  - [`start`](#start) 如果该组件第一次启用，则在所有组件的 update 之前调用。通常用于需要在所有组件的 onLoad 初始化完毕后执行的逻辑。
  - [`onEnable`](#onenable) 当该组件被启用，并且它的节点也激活时。
  - [`onDisable`](#ondisable) 当该组件被禁用或节点变为无效时调用。
  - [`onDestroy`](#ondestroy) 当该组件被销毁时调用
  - [`onFocusInEditor`](#onfocusineditor) 
  - [`onLostFocusInEditor`](#onlostfocusineditor) 
  - [`resetInEditor`](#resetineditor) 用来初始化组件或节点的一些属性，当该组件被第一次添加到节点上或用户点击了它的 Reset 菜单时调用。这个回调只会在编辑器下调用。
  - [`addComponent`](#addcomponent) 向节点添加一个组件类，你还可以通过传入脚本的名称来添加组件。
  - [`getComponent`](#getcomponent) 获取节点上指定类型的组件，如果节点有附加指定类型的组件，则返回，如果没有则为空。<br/>
传入参数也可以是脚本的名称。
  - [`getComponents`](#getcomponents) 返回节点上指定类型的所有组件。
  - [`getComponentInChildren`](#getcomponentinchildren) 递归查找所有子节点中第一个匹配指定类型的组件。
  - [`getComponentsInChildren`](#getcomponentsinchildren) 递归查找自身或所有子节点中指定类型的组件
  - [`_getLocalBounds`](#getlocalbounds) 如果组件的包围盒与节点不同，您可以实现该方法以提供自定义的轴向对齐的包围盒（AABB），
以便编辑器的场景视图可以正确地执行点选测试。
  - [`onRestore`](#onrestore) onRestore 是用户在检查器菜单点击 Reset 时，对此组件执行撤消操作后调用的。<br/>
<br/>
如果组件包含了“内部状态”（不在 CCClass 属性中定义的临时成员变量），那么你可能需要实现该方法。<br/>
<br/>
编辑器执行撤销/重做操作时，将调用组件的 get set 来录制和还原组件的状态。
然而，在极端的情况下，它可能无法良好运作。<br/>
那么你就应该实现这个方法，手动根据组件的属性同步“内部状态”。
一旦你实现这个方法，当用户撤销或重做时，组件的所有 get set 都不会再被调用。
这意味着仅仅指定了默认值的属性将被编辑器记录和还原。<br/>
<br/>
同样的，编辑可能无法在极端情况下正确地重置您的组件。<br/>
于是如果你需要支持组件重置菜单，你需要在该方法中手工同步组件属性到“内部状态”。<br/>
一旦你实现这个方法，组件的所有 get set 都不会在重置操作时被调用。
这意味着仅仅指定了默认值的属性将被编辑器重置。
<br/>
此方法仅在编辑器下会被调用。
  - [`schedule`](#schedule) 调度一个自定义的回调函数。<br/>
如果回调函数已调度，那么将不会重复调度它，只会更新时间间隔参数。
  - [`scheduleOnce`](#scheduleonce) 调度一个只运行一次的回调函数，可以指定 0 让回调函数在下一帧立即执行或者在一定的延时之后执行。
  - [`unschedule`](#unschedule) 取消调度一个自定义的回调函数。
  - [`unscheduleAllCallbacks`](#unscheduleallcallbacks) 取消调度所有已调度的回调函数：定制的回调函数以及 'update' 回调函数。动作不受此方法影响。
  - [`destroy`](#destroy) 销毁该对象，并释放所有它对其它对象的引用。<br/>
销毁后，CCObject 不再可用。您可以在访问对象之前使用 cc.isValid(obj) 来检查对象是否已被销毁。
实际销毁操作会延迟到当前帧渲染前执行。
  - [`_destruct`](#destruct) Clear all references in the instance.

NOTE: this method will not clear the getter or setter functions which defined in the instance of CCObject.
      You can override the _destruct method if you need, for example:
      _destruct: function () {
          for (var key in this) {
              if (this.hasOwnProperty(key)) {
                  switch (typeof this[key]) {
                      case 'string':
                          this[key] = '';
                          break;
                      case 'object':
                      case 'function':
                          this[key] = null;
                          break;
              }
          }
      }
  - [`_onPreDestroy`](#onpredestroy) Called before the object being destroyed.
  - [`_serialize`](#serialize) The customized serialization for this object. (Editor Only)
  - [`_deserialize`](#deserialize) Init this object from the custom serialized data.



##### 事件

  - [`page-turning`](#page-turning) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-to-top`](#scroll-to-top) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-to-bottom`](#scroll-to-bottom) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-to-left`](#scroll-to-left) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-to-right`](#scroll-to-right) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scrolling`](#scrolling) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`bounce-bottom`](#bounce-bottom) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`bounce-top`](#bounce-top) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`bounce-left`](#bounce-left) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`bounce-right`](#bounce-right) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-ended`](#scroll-ended) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`touch-up`](#touch-up) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。
  - [`scroll-began`](#scroll-began) 注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。


### Details


#### 属性（properties）


##### sizeMode

> 页面视图中每个页面大小类型

| meta | description |
|------|-------------|
| 类型 | <a href="../enums/PageView.SizeMode.html" class="crosslink">PageView.SizeMode</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:111](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L111) |



##### direction

> 页面视图滚动类型

| meta | description |
|------|-------------|
| 类型 | <a href="../enums/PageView.Direction.html" class="crosslink">PageView.Direction</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:125](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L125) |



##### scrollThreshold

> 滚动临界值，默认单位百分比，当拖拽超出该数值时，松开会自动滚动下一页，小于时则还原。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:139](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L139) |



##### autoPageTurningThreshold

> 快速滑动翻页临界值。
当用户快速滑动时，会根据滑动开始和结束的距离与时间计算出一个速度值，
该值与此临界值相比较，如果大于临界值，则进行自动翻页。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:154](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L154) |



##### pageTurningEventTiming

> 设置 PageView PageTurning 事件的发送时机。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:171](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L171) |



##### indicator

> 页面视图指示器组件

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/PageViewIndicator.html" class="crosslink">PageViewIndicator</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:183](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L183) |



##### pageTurningSpeed

> 每个页面翻页时所需时间。单位：秒

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:199](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L199) |



##### pageEvents

> 滚动视图的事件回调函数

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Component.EventHandler.html" class="crosslink">Component.EventHandler[]</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:210](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L210) |



##### content

> 可滚动展示内容的节点。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Node.html" class="crosslink">Node</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:200](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L200) |



##### horizontal

> 是否开启水平滚动。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:211](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L211) |



##### vertical

> 是否开启垂直滚动。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:222](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L222) |



##### inertia

> 是否开启滚动惯性。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:233](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L233) |



##### brake

> 开启惯性后，在用户停止触摸后滚动多快停止，0表示永不停止，1表示立刻停止。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:243](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L243) |



##### elastic

> 是否允许滚动内容超过边界，并在停止触摸后回弹。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:258](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L258) |



##### bounceDuration

> 回弹持续的时间，0 表示将立即反弹。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:269](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L269) |



##### horizontalScrollBar

> 水平滚动的 ScrollBar。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Scrollbar.html" class="crosslink">Scrollbar</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:280](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L280) |



##### verticalScrollBar

> 垂直滚动的 ScrollBar。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Scrollbar.html" class="crosslink">Scrollbar</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:298](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L298) |



##### scrollEvents

> 滚动视图的事件回调函数

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Component.EventHandler.html" class="crosslink">Component.EventHandler[]</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:316](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L316) |



##### cancelInnerEvents

> 如果这个属性被设置为 true，那么滚动行为会取消子节点上注册的触摸事件，默认被设置为 true。
注意，子节点上的 touchstart 事件仍然会触发，触点移动距离非常短的情况下 touchmove 和 touchend 也不会受影响。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:327](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L327) |



##### __eventTargets

> Register all related EventTargets,
all event callbacks will be removed in _onPreDestroy

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Array" class="crosslink external" target="_blank">Array</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:61](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L61) |



##### node

> 该组件被附加到的节点。组件总会附加到一个节点。

| meta | description |
|------|-------------|
| 类型 | <a href="../classes/Node.html" class="crosslink">Node</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:75](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L75) |

##### 示例

```js
cc.log(comp.node);
```


##### uuid

> 组件的 uuid，用于编辑器。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:111](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L111) |

##### 示例

```js
cc.log(comp.uuid);
```


##### _enabled

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:159](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L159) |



##### enabled

> 表示该组件自身是否启用。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:166](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L166) |

##### 示例

```js
comp.enabled = true;
cc.log(comp.enabled);
```


##### enabledInHierarchy

> 表示该组件是否被启用并且所在的节点也处于激活状态。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:197](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L197) |

##### 示例

```js
cc.log(comp.enabledInHierarchy);
```


##### _isOnLoadCalled

> 返回一个值用来判断 onLoad 是否被调用过，不等于 0 时调用过，等于 0 时未调用。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:213](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L213) |

##### 示例

```js
cc.log(this._isOnLoadCalled > 0);
```


##### _name

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:50](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L50) |



##### _objFlags

> 

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:57](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L57) |



##### name

> 该对象的名称。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:208](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L208) |

##### 示例

```js
obj.name = "New Obj";
```


##### isValid

> 表示该对象是否可用（被销毁后将不可用）。

| meta | description |
|------|-------------|
| 类型 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> |
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:225](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L225) |

##### 示例

```js
cc.log(obj.isValid);
```





<!-- Method Block -->
#### 方法


##### getCurrentPageIndex

返回当前页面索引

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:257](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L257) |



##### setCurrentPageIndex

设置当前页面索引

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:267](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L267) |

###### 参数列表
- index <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### getPages

返回视图中的所有页面

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Node.html" class="crosslink">Node[]</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:277](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L277) |



##### addPage

在当前页面视图的尾部插入一个新视图

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:287](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L287) |

###### 参数列表
- page <a href="../classes/Node.html" class="crosslink">Node</a> 


##### insertPage

将页面插入指定位置中

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:301](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L301) |

###### 参数列表
- page <a href="../classes/Node.html" class="crosslink">Node</a> 
- index <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### removePage

移除指定页面

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:321](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L321) |

###### 参数列表
- page <a href="../classes/Node.html" class="crosslink">Node</a> 


##### removePageAtIndex

移除指定下标的页面

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:337](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L337) |

###### 参数列表
- index <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### removeAllPages

移除所有页面

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:353](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L353) |



##### scrollToPage

滚动到指定页面

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js:367](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCPageView.js#L367) |

###### 参数列表
- idx <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> index of page.
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> scrolling time


##### scrollToBottom

视图内容将在规定时间内滚动到视图底部。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:345](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L345) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the bottom boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the bottom of the view.
scrollView.scrollToBottom(0.1);
```

##### scrollToTop

视图内容将在规定时间内滚动到视图顶部。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:370](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L370) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the top boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the top of the view.
scrollView.scrollToTop(0.1);
```

##### scrollToLeft

视图内容将在规定时间内滚动到视图左边。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:395](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L395) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the left boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the left of the view.
scrollView.scrollToLeft(0.1);
```

##### scrollToRight

视图内容将在规定时间内滚动到视图右边。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:420](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L420) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the right boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the right of the view.
scrollView.scrollToRight(0.1);
```

##### scrollToTopLeft

视图内容将在规定时间内滚动到视图左上角。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:445](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L445) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the top left boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the upper left corner of the view.
scrollView.scrollToTopLeft(0.1);
```

##### scrollToTopRight

视图内容将在规定时间内滚动到视图右上角。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:470](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L470) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the top right boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the top right corner of the view.
scrollView.scrollToTopRight(0.1);
```

##### scrollToBottomLeft

视图内容将在规定时间内滚动到视图左下角。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:495](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L495) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the bottom left boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the lower left corner of the view.
scrollView.scrollToBottomLeft(0.1);
```

##### scrollToBottomRight

视图内容将在规定时间内滚动到视图右下角。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:520](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L520) |

###### 参数列表
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the bottom right boundary immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to the lower right corner of the view.
scrollView.scrollToBottomRight(0.1);
```

##### scrollToOffset

视图内容在规定时间内将滚动到 ScrollView 相对左上角原点的偏移位置, 如果 timeInSecond参数不传，则立即滚动到指定偏移位置。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:546](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L546) |

###### 参数列表
- offset <a href="../classes/Vec2.html" class="crosslink">Vec2</a> A Vec2, the value of which each axis between 0 and maxScrollOffset
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the specific offset of ScrollView immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to middle position in 0.1 second in x-axis
var maxScrollOffset = this.getMaxScrollOffset();
scrollView.scrollToOffset(cc.p(maxScrollOffset.x / 2, 0), 0.1);
```

##### getScrollOffset

获取滚动视图相对于左上角原点的当前滚动偏移

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:580](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L580) |



##### getMaxScrollOffset

获取滚动视图最大可以滚动的偏移量

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:593](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L593) |



##### scrollToPercentHorizontal

视图内容在规定时间内将滚动到 ScrollView 水平方向的百分比位置上。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:610](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L610) |

###### 参数列表
- percent <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> A value between 0 and 1.
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the horizontal percent position of ScrollView immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Scroll to middle position.
scrollView.scrollToBottomRight(0.5, 0.1);
```

##### scrollTo

视图内容在规定时间内进行垂直方向和水平方向的滚动，并且滚动到指定百分比位置上。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:636](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L636) |

###### 参数列表
- anchor <a href="../classes/Vec2.html" class="crosslink">Vec2</a> A point which will be clamp between cc.p(0,0) and cc.p(1,1).
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the percent position of ScrollView immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.

##### 示例

```js
// Vertical scroll to the bottom of the view.
scrollView.scrollTo(cc.p(0, 1), 0.1);

// Horizontal scroll to view right.
scrollView.scrollTo(cc.p(1, 0), 0.1);
```

##### scrollToPercentVertical

视图内容在规定时间内滚动到 ScrollView 垂直方向的百分比位置上。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:665](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L665) |

###### 参数列表
- percent <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> A value between 0 and 1.
- timeInSecond <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Scroll time in second, if you don't pass timeInSecond,
the content will jump to the vertical percent position of ScrollView immediately.
- attenuated <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether the scroll acceleration attenuated, default is true.
// Scroll to middle position.
scrollView.scrollToPercentVertical(0.5, 0.1);


##### stopAutoScroll

停止自动滚动, 调用此 API 可以让 Scrollview 立即停止滚动

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:690](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L690) |



##### setContentPosition

设置当前视图内容的坐标点。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:700](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L700) |

###### 参数列表
- position <a href="../classes/Vec2.html" class="crosslink">Vec2</a> The position in content's parent space.


##### getContentPosition

获取当前视图内容的坐标点。

| meta | description |
|------|-------------|
| 返回 | Position 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:715](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L715) |



##### isScrolling

用户是否在拖拽当前滚动视图

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:725](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L725) |



##### isAutoScrolling

当前滚动视图是否在惯性滚动

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js:735](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCScrollView.js#L735) |



##### update

如果该组件启用，则每帧调用 update。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:234](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L234) |

###### 参数列表
- dt <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> the delta time in seconds it took to complete the last frame


##### lateUpdate

如果该组件启用，则每帧调用 LateUpdate。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:243](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L243) |



##### __preload

`__preload` is called before every onLoad.
It is used to initialize the builtin components internally,
to avoid checking whether onLoad is called before every public method calls.
This method should be removed if script priority is supported.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:251](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L251) |



##### onLoad

当附加到一个激活的节点上或者其节点第一次激活时候调用。onLoad 总是会在任何 start 方法调用前执行，这能用于安排脚本的初始化顺序。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:262](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L262) |



##### start

如果该组件第一次启用，则在所有组件的 update 之前调用。通常用于需要在所有组件的 onLoad 初始化完毕后执行的逻辑。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:273](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L273) |



##### onEnable

当该组件被启用，并且它的节点也激活时。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:284](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L284) |



##### onDisable

当该组件被禁用或节点变为无效时调用。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:292](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L292) |



##### onDestroy

当该组件被销毁时调用

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:300](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L300) |



##### onFocusInEditor



| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:308](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L308) |



##### onLostFocusInEditor



| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:313](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L313) |



##### resetInEditor

用来初始化组件或节点的一些属性，当该组件被第一次添加到节点上或用户点击了它的 Reset 菜单时调用。这个回调只会在编辑器下调用。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:318](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L318) |



##### addComponent

向节点添加一个组件类，你还可以通过传入脚本的名称来添加组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:328](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L328) |

###### 参数列表
- typeOrClassName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> the constructor or the class name of the component to add

##### 示例

```js
var sprite = node.addComponent(cc.Sprite);
var test = node.addComponent("Test");
```

##### getComponent

获取节点上指定类型的组件，如果节点有附加指定类型的组件，则返回，如果没有则为空。<br/>
传入参数也可以是脚本的名称。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:346](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L346) |

###### 参数列表
- typeOrClassName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
// get sprite component.
var sprite = node.getComponent(cc.Sprite);
// get custom test calss.
var test = node.getComponent("Test");
```

##### getComponents

返回节点上指定类型的所有组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:370](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L370) |

###### 参数列表
- typeOrClassName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprites = node.getComponents(cc.Sprite);
var tests = node.getComponents("Test");
```

##### getComponentInChildren

递归查找所有子节点中第一个匹配指定类型的组件。

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:388](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L388) |

###### 参数列表
- typeOrClassName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprite = node.getComponentInChildren(cc.Sprite);
var Test = node.getComponentInChildren("Test");
```

##### getComponentsInChildren

递归查找自身或所有子节点中指定类型的组件

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Component.html" class="crosslink">Component[]</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:406](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L406) |

###### 参数列表
- typeOrClassName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 

##### 示例

```js
var sprites = node.getComponentsInChildren(cc.Sprite);
var tests = node.getComponentsInChildren("Test");
```

##### _getLocalBounds

如果组件的包围盒与节点不同，您可以实现该方法以提供自定义的轴向对齐的包围盒（AABB），
以便编辑器的场景视图可以正确地执行点选测试。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:426](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L426) |

###### 参数列表
- out_rect <a href="../classes/Rect.html" class="crosslink">Rect</a> the Rect to receive the bounding box


##### onRestore

onRestore 是用户在检查器菜单点击 Reset 时，对此组件执行撤消操作后调用的。<br/>
<br/>
如果组件包含了“内部状态”（不在 CCClass 属性中定义的临时成员变量），那么你可能需要实现该方法。<br/>
<br/>
编辑器执行撤销/重做操作时，将调用组件的 get set 来录制和还原组件的状态。
然而，在极端的情况下，它可能无法良好运作。<br/>
那么你就应该实现这个方法，手动根据组件的属性同步“内部状态”。
一旦你实现这个方法，当用户撤销或重做时，组件的所有 get set 都不会再被调用。
这意味着仅仅指定了默认值的属性将被编辑器记录和还原。<br/>
<br/>
同样的，编辑可能无法在极端情况下正确地重置您的组件。<br/>
于是如果你需要支持组件重置菜单，你需要在该方法中手工同步组件属性到“内部状态”。<br/>
一旦你实现这个方法，组件的所有 get set 都不会在重置操作时被调用。
这意味着仅仅指定了默认值的属性将被编辑器重置。
<br/>
此方法仅在编辑器下会被调用。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:439](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L439) |



##### schedule

调度一个自定义的回调函数。<br/>
如果回调函数已调度，那么将不会重复调度它，只会更新时间间隔参数。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:541](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L541) |

###### 参数列表
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> The callback function
- interval <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Tick interval in seconds. 0 means tick every frame.
- repeat <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The selector will be executed (repeat + 1) times, you can use cc.macro.REPEAT_FOREVER for tick infinitely.
- delay <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### 示例

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.schedule(timeCallback, 1);
```

##### scheduleOnce

调度一个只运行一次的回调函数，可以指定 0 让回调函数在下一帧立即执行或者在一定的延时之后执行。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:578](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L578) |

###### 参数列表
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector
- delay <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The amount of time that the first tick will wait before execution.

##### 示例

```js
var timeCallback = function (dt) {
  cc.log("time: " + dt);
}
this.scheduleOnce(timeCallback, 2);
```

##### unschedule

取消调度一个自定义的回调函数。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:595](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L595) |

###### 参数列表
- callback_fn <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">function</a> A function wrapped as a selector

##### 示例

```js
this.unschedule(_callback);
```

##### unscheduleAllCallbacks

取消调度所有已调度的回调函数：定制的回调函数以及 'update' 回调函数。动作不受此方法影响。

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js:611](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/components/CCComponent.js#L611) |


##### 示例

```js
this.unscheduleAllCallbacks();
```

##### destroy

销毁该对象，并释放所有它对其它对象的引用。<br/>
销毁后，CCObject 不再可用。您可以在访问对象之前使用 cc.isValid(obj) 来检查对象是否已被销毁。
实际销毁操作会延迟到当前帧渲染前执行。

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:246](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L246) |


##### 示例

```js
obj.destroy();
```

##### _destruct

Clear all references in the instance.

NOTE: this method will not clear the getter or setter functions which defined in the instance of CCObject.
      You can override the _destruct method if you need, for example:
      _destruct: function () {
          for (var key in this) {
              if (this.hasOwnProperty(key)) {
                  switch (typeof this[key]) {
                      case 'string':
                          this[key] = '';
                          break;
                      case 'object':
                      case 'function':
                          this[key] = null;
                          break;
              }
          }
      }

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:379](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L379) |



##### _onPreDestroy

Called before the object being destroyed.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:412](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L412) |



##### _serialize

The customized serialization for this object. (Editor Only)

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">object</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:437](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L437) |

###### 参数列表
- exporting <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 


##### _deserialize

Init this object from the custom serialized data.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js:447](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCObject.js#L447) |

###### 参数列表
- data <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> the serialized json data
- ctx _Deserializer 




#### 事件

### `page-turning` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-to-top` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-to-bottom` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-to-left` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-to-right` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scrolling` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `bounce-bottom` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `bounce-top` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `bounce-left` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `bounce-right` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-ended` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `touch-up` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details




### `scroll-began` Event



模块: [cc](../modules/cc.md)




注意：此事件是从该组件所属的 Node 上面派发出来的，需要用 node.on 来监听。

### 索引







### Details





