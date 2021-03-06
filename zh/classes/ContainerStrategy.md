## `ContainerStrategy` 类型



模块: [_decorator](../modules/_decorator.md)
父模块: [cc](../modules/cc.md)




<p>cc.ContainerStrategy class is the root strategy class of container's scale strategy,
it controls the behavior of how to scale the cc.container and cc.game.canvas object</p>

### 索引



##### 方法

  - [`preApply`](#preapply) Manipulation before appling the strategy
  - [`apply`](#apply) Function to apply this strategy
  - [`postApply`](#postapply) Manipulation after applying the strategy



### Details




<!-- Method Block -->
#### 方法


##### preApply

Manipulation before appling the strategy

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:1021](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L1021) |

###### 参数列表
- view <a href="../classes/View.html" class="crosslink">View</a> The target view


##### apply

Function to apply this strategy

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:1029](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L1029) |

###### 参数列表
- view <a href="../classes/View.html" class="crosslink">View</a> 
- designedResolution <a href="../classes/Size.html" class="crosslink">Size</a> 


##### postApply

Manipulation after applying the strategy

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:1038](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L1038) |

###### 参数列表
- view <a href="../classes/View.html" class="crosslink">View</a> The target view



