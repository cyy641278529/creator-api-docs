## `ProtocolCustom` Class

Extends [`PluginProtocol`](PluginProtocol.md)


Module: [anysdk](../modules/anysdk.md)




custom protocol

### Index



##### Methods

  - [`setListener`](#setlistener) set listener
  - [`getListener`](#getlistener) get listener
  - [`isFunctionSupported`](#isfunctionsupported) Check whether the function is supported
  - [`getPluginName`](#getpluginname) get plugin name
  - [`getPluginVersion`](#getpluginversion) get plugin version
  - [`getSDKVersion`](#getsdkversion) get SDK version
  - [`callFuncWithParam`](#callfuncwithparam) void methods for reflections with parameter
  - [`callStringFuncWithParam`](#callstringfuncwithparam) String methods for reflections with parameter
  - [`callIntFuncWithParam`](#callintfuncwithparam) int methods for reflections with parameter
  - [`callBoolFuncWithParam`](#callboolfuncwithparam) boolean methods for reflections with parameter
  - [`callFloatFuncWithParam`](#callfloatfuncwithparam) float methods for reflections with parameter



### Details




<!-- Method Block -->
#### Methods


##### setListener

set listener

| meta | description |
|------|-------------|
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:1752](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L1752) |

###### Parameters
- listener <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> 
- target <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> 


##### getListener

get listener

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:1764](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L1764) |



##### isFunctionSupported

Check whether the function is supported

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">boolean</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:327](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L327) |

###### Parameters
- functionName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getPluginName

get plugin name

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:341](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L341) |



##### getPluginVersion

get plugin version

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:353](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L353) |



##### getSDKVersion

get SDK version

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:365](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L365) |



##### callFuncWithParam

void methods for reflections with parameter

| meta | description |
|------|-------------|
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:377](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L377) |

###### Parameters
- funName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- args <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; anysdk.PluginParam optional arguments


##### callStringFuncWithParam

String methods for reflections with parameter

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:390](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L390) |

###### Parameters
- funName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- args <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; anysdk.PluginParam optional arguments


##### callIntFuncWithParam

int methods for reflections with parameter

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:405](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L405) |

###### Parameters
- funName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- args <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; anysdk.PluginParam optional arguments


##### callBoolFuncWithParam

boolean methods for reflections with parameter

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">boolean</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:420](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L420) |

###### Parameters
- funName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- args <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; anysdk.PluginParam optional arguments


##### callFloatFuncWithParam

float methods for reflections with parameter

| meta | description |
|------|-------------|
| Returns | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| Defined in | [https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js:435](https:/github.com/cocos-creator/engine/blob/master/extensions/anysdk/jsb_anysdk.js#L435) |

###### Parameters
- funName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
- args <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> &#124; anysdk.PluginParam optional arguments



