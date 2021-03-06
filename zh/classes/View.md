## `View` 类型



模块: [_decorator](../modules/_decorator.md)
父模块: [cc](../modules/cc.md)




cc.view is the singleton object which represents the game window.<br/>
It's main task include: <br/>
 - Apply the design resolution policy<br/>
 - Provide interaction with the window, like resize event on web, retina display support, etc...<br/>
 - Manage the game view port which can be different with the window<br/>
 - Manage the content scale and translation<br/>
<br/>
Since the cc.view is a singleton, you don't need to call any constructor or create functions,<br/>
the standard way to use it is by calling:<br/>
 - cc.view.methodName(); <br/>

### 索引



##### 方法

  - [`setTargetDensityDPI`](#settargetdensitydpi) <p>
Sets view's target-densitydpi for android mobile browser. it can be set to:           <br/>
  1. cc.macro.DENSITYDPI_DEVICE, value is "device-dpi"                                      <br/>
  2. cc.macro.DENSITYDPI_HIGH, value is "high-dpi"  (default value)                         <br/>
  3. cc.macro.DENSITYDPI_MEDIUM, value is "medium-dpi" (browser's default value)            <br/>
  4. cc.macro.DENSITYDPI_LOW, value is "low-dpi"                                            <br/>
  5. Custom value, e.g: "480"                                                         <br/>
</p>
  - [`getTargetDensityDPI`](#gettargetdensitydpi) Returns the current target-densitydpi value of cc.view.
  - [`resizeWithBrowserSize`](#resizewithbrowsersize) Sets whether resize canvas automatically when browser's size changed.<br/>
Useful only on web.
  - [`setResizeCallback`](#setresizecallback) Sets the callback function for cc.view's resize action,<br/>
this callback will be invoked before applying resolution policy, <br/>
so you can do any additional modifications within the callback.<br/>
Useful only on web.
  - [`setOrientation`](#setorientation) Sets the orientation of the game, it can be landscape, portrait or auto.
When set it to landscape or portrait, and screen w/h ratio doesn't fit,
cc.view will automatically rotate the game canvas using CSS.
Note that this function doesn't have any effect in native,
in native, you need to set the application orientation in native project settings
  - [`adjustViewPort`](#adjustviewport) Sets whether the engine modify the "viewport" meta in your web page.<br/>
It's enabled by default, we strongly suggest you not to disable it.<br/>
And even when it's enabled, you can still set your own "viewport" meta, it won't be overridden<br/>
Only useful on web
  - [`enableRetina`](#enableretina) Retina support is enabled by default for Apple device but disabled for other devices,<br/>
it takes effect only when you called setDesignResolutionPolicy<br/>
Only useful on web
  - [`isRetinaEnabled`](#isretinaenabled) Check whether retina display is enabled.<br/>
Only useful on web
  - [`enableAntiAlias`](#enableantialias) 控制抗锯齿是否开启
  - [`isAntiAliasEnabled`](#isantialiasenabled) 返回当前是否抗锯齿
  - [`enableAutoFullScreen`](#enableautofullscreen) If enabled, the application will try automatically to enter full screen mode on mobile devices<br/>
You can pass true as parameter to enable it and disable it by passing false.<br/>
Only useful on web
  - [`isAutoFullScreenEnabled`](#isautofullscreenenabled) Check whether auto full screen is enabled.<br/>
Only useful on web
  - [`isViewReady`](#isviewready) Get whether render system is ready(no matter opengl or canvas),<br/>
this name is for the compatibility with cocos2d-x, subclass must implement this method.
  - [`setContentTranslateLeftTop`](#setcontenttranslatelefttop) Sets the resolution translate on View.
  - [`getContentTranslateLeftTop`](#getcontenttranslatelefttop) Returns the resolution translate on View
  - [`getFrameSize`](#getframesize) Returns the frame size of the view.<br/>
On native platforms, it returns the screen size since the view is a fullscreen view.<br/>
On web, it returns the size of the canvas's outer DOM element.
  - [`setFrameSize`](#setframesize) On native, it sets the frame size of view.<br/>
On web, it sets the size of the canvas's outer DOM element.
  - [`getVisibleSize`](#getvisiblesize) Returns the visible area size of the view port.
  - [`getVisibleSizeInPixel`](#getvisiblesizeinpixel) Returns the visible area size of the view port.
  - [`getVisibleOrigin`](#getvisibleorigin) Returns the visible origin of the view port.
  - [`getVisibleOriginInPixel`](#getvisibleorigininpixel) Returns the visible origin of the view port.
  - [`canSetContentScaleFactor`](#cansetcontentscalefactor) Returns whether developer can set content's scale factor.
  - [`getResolutionPolicy`](#getresolutionpolicy) Returns the current resolution policy
  - [`setResolutionPolicy`](#setresolutionpolicy) Sets the current resolution policy
  - [`setDesignResolutionSize`](#setdesignresolutionsize) Sets the resolution policy with designed view size in points.<br/>
The resolution policy include: <br/>
[1] ResolutionExactFit       Fill screen by stretch-to-fit: if the design resolution ratio of width to height is different from the screen resolution ratio, your game view will be stretched.<br/>
[2] ResolutionNoBorder       Full screen without black border: if the design resolution ratio of width to height is different from the screen resolution ratio, two areas of your game view will be cut.<br/>
[3] ResolutionShowAll        Full screen with black border: if the design resolution ratio of width to height is different from the screen resolution ratio, two black borders will be shown.<br/>
[4] ResolutionFixedHeight    Scale the content's height to screen's height and proportionally scale its width<br/>
[5] ResolutionFixedWidth     Scale the content's width to screen's width and proportionally scale its height<br/>
[cc.ResolutionPolicy]        [Web only feature] Custom resolution policy, constructed by cc.ResolutionPolicy<br/>
  - [`getDesignResolutionSize`](#getdesignresolutionsize) Returns the designed size for the view.
Default resolution size is the same as 'getFrameSize'.
  - [`setRealPixelResolution`](#setrealpixelresolution) Sets the container to desired pixel resolution and fit the game content to it.
This function is very useful for adaptation in mobile browsers.
In some HD android devices, the resolution is very high, but its browser performance may not be very good.
In this case, enabling retina display is very costy and not suggested, and if retina is disabled, the image may be blurry.
But this API can be helpful to set a desired pixel resolution which is in between.
This API will do the following:
    1. Set viewport's width to the desired width in pixel
    2. Set body width to the exact pixel resolution
    3. The resolution policy will be reset with designed view size in points.
  - [`setViewPortInPoints`](#setviewportinpoints) Sets view port rectangle with points.
  - [`setScissorInPoints`](#setscissorinpoints) Sets Scissor rectangle with points.
  - [`isScissorEnabled`](#isscissorenabled) Returns whether GL_SCISSOR_TEST is enable
  - [`getScissorRect`](#getscissorrect) Returns the current scissor rectangle
  - [`setViewName`](#setviewname) Sets the name of the view
  - [`getViewName`](#getviewname) Returns the name of the view
  - [`getViewPortRect`](#getviewportrect) Returns the view port rectangle.
  - [`getScaleX`](#getscalex) Returns scale factor of the horizontal direction (X axis).
  - [`getScaleY`](#getscaley) Returns scale factor of the vertical direction (Y axis).
  - [`getDevicePixelRatio`](#getdevicepixelratio) Returns device pixel ratio for retina display.
  - [`convertToLocationInView`](#converttolocationinview) Returns the real location in view for a translation based on a related position
  - [`_getInstance`](#getinstance) 



### Details




<!-- Method Block -->
#### 方法


##### setTargetDensityDPI

<p>
Sets view's target-densitydpi for android mobile browser. it can be set to:           <br/>
  1. cc.macro.DENSITYDPI_DEVICE, value is "device-dpi"                                      <br/>
  2. cc.macro.DENSITYDPI_HIGH, value is "high-dpi"  (default value)                         <br/>
  3. cc.macro.DENSITYDPI_MEDIUM, value is "medium-dpi" (browser's default value)            <br/>
  4. cc.macro.DENSITYDPI_LOW, value is "low-dpi"                                            <br/>
  5. Custom value, e.g: "480"                                                         <br/>
</p>

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:223](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L223) |

###### 参数列表
- densityDPI <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getTargetDensityDPI

Returns the current target-densitydpi value of cc.view.

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:241](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L241) |



##### resizeWithBrowserSize

Sets whether resize canvas automatically when browser's size changed.<br/>
Useful only on web.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:250](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L250) |

###### 参数列表
- enabled <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Whether enable automatic resize with browser's resize event


##### setResizeCallback

Sets the callback function for cc.view's resize action,<br/>
this callback will be invoked before applying resolution policy, <br/>
so you can do any additional modifications within the callback.<br/>
Useful only on web.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:274](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L274) |

###### 参数列表
- callback <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Function" class="crosslink external" target="_blank">Function</a> &#124; Null The callback function


##### setOrientation

Sets the orientation of the game, it can be landscape, portrait or auto.
When set it to landscape or portrait, and screen w/h ratio doesn't fit,
cc.view will automatically rotate the game canvas using CSS.
Note that this function doesn't have any effect in native,
in native, you need to set the application orientation in native project settings

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:288](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L288) |

###### 参数列表
- orientation <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Possible values: cc.macro.ORIENTATION_LANDSCAPE | cc.macro.ORIENTATION_PORTRAIT | cc.macro.ORIENTATION_AUTO


##### adjustViewPort

Sets whether the engine modify the "viewport" meta in your web page.<br/>
It's enabled by default, we strongly suggest you not to disable it.<br/>
And even when it's enabled, you can still set your own "viewport" meta, it won't be overridden<br/>
Only useful on web

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:403](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L403) |

###### 参数列表
- enabled <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Enable automatic modification to "viewport" meta


##### enableRetina

Retina support is enabled by default for Apple device but disabled for other devices,<br/>
it takes effect only when you called setDesignResolutionPolicy<br/>
Only useful on web

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:415](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L415) |

###### 参数列表
- enabled <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Enable or disable retina display


##### isRetinaEnabled

Check whether retina display is enabled.<br/>
Only useful on web

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:426](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L426) |



##### enableAntiAlias

控制抗锯齿是否开启

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:436](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L436) |

###### 参数列表
- enabled <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Enable or not anti-alias


##### isAntiAliasEnabled

返回当前是否抗锯齿

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:476](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L476) |



##### enableAutoFullScreen

If enabled, the application will try automatically to enter full screen mode on mobile devices<br/>
You can pass true as parameter to enable it and disable it by passing false.<br/>
Only useful on web

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:485](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L485) |

###### 参数列表
- enabled <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> Enable or disable auto full screen on mobile devices


##### isAutoFullScreenEnabled

Check whether auto full screen is enabled.<br/>
Only useful on web

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:506](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L506) |



##### isViewReady

Get whether render system is ready(no matter opengl or canvas),<br/>
this name is for the compatibility with cocos2d-x, subclass must implement this method.

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:516](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L516) |



##### setContentTranslateLeftTop

Sets the resolution translate on View.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:536](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L536) |

###### 参数列表
- offsetLeft <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- offsetTop <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### getContentTranslateLeftTop

Returns the resolution translate on View

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Size.html" class="crosslink">Size</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:546](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L546) |



##### getFrameSize

Returns the frame size of the view.<br/>
On native platforms, it returns the screen size since the view is a fullscreen view.<br/>
On web, it returns the size of the canvas's outer DOM element.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Size.html" class="crosslink">Size</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:589](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L589) |



##### setFrameSize

On native, it sets the frame size of view.<br/>
On web, it sets the size of the canvas's outer DOM element.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:600](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L600) |

###### 参数列表
- width <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- height <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### getVisibleSize

Returns the visible area size of the view port.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Size.html" class="crosslink">Size</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:616](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L616) |



##### getVisibleSizeInPixel

Returns the visible area size of the view port.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Size.html" class="crosslink">Size</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:625](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L625) |



##### getVisibleOrigin

Returns the visible origin of the view port.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:635](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L635) |



##### getVisibleOriginInPixel

Returns the visible origin of the view port.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:644](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L644) |



##### canSetContentScaleFactor

Returns whether developer can set content's scale factor.

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:654](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L654) |



##### getResolutionPolicy

Returns the current resolution policy

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/ResolutionPolicy.html" class="crosslink">ResolutionPolicy</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:663](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L663) |



##### setResolutionPolicy

Sets the current resolution policy

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:673](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L673) |

###### 参数列表
- resolutionPolicy <a href="../classes/ResolutionPolicy.html" class="crosslink">ResolutionPolicy</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### setDesignResolutionSize

Sets the resolution policy with designed view size in points.<br/>
The resolution policy include: <br/>
[1] ResolutionExactFit       Fill screen by stretch-to-fit: if the design resolution ratio of width to height is different from the screen resolution ratio, your game view will be stretched.<br/>
[2] ResolutionNoBorder       Full screen without black border: if the design resolution ratio of width to height is different from the screen resolution ratio, two areas of your game view will be cut.<br/>
[3] ResolutionShowAll        Full screen with black border: if the design resolution ratio of width to height is different from the screen resolution ratio, two black borders will be shown.<br/>
[4] ResolutionFixedHeight    Scale the content's height to screen's height and proportionally scale its width<br/>
[5] ResolutionFixedWidth     Scale the content's width to screen's width and proportionally scale its height<br/>
[cc.ResolutionPolicy]        [Web only feature] Custom resolution policy, constructed by cc.ResolutionPolicy<br/>

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:700](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L700) |

###### 参数列表
- width <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Design resolution width.
- height <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Design resolution height.
- resolutionPolicy <a href="../classes/ResolutionPolicy.html" class="crosslink">ResolutionPolicy</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The resolution policy desired


##### getDesignResolutionSize

Returns the designed size for the view.
Default resolution size is the same as 'getFrameSize'.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Size.html" class="crosslink">Size</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:790](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L790) |



##### setRealPixelResolution

Sets the container to desired pixel resolution and fit the game content to it.
This function is very useful for adaptation in mobile browsers.
In some HD android devices, the resolution is very high, but its browser performance may not be very good.
In this case, enabling retina display is very costy and not suggested, and if retina is disabled, the image may be blurry.
But this API can be helpful to set a desired pixel resolution which is in between.
This API will do the following:
    1. Set viewport's width to the desired width in pixel
    2. Set body width to the exact pixel resolution
    3. The resolution policy will be reset with designed view size in points.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:800](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L800) |

###### 参数列表
- width <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Design resolution width.
- height <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> Design resolution height.
- resolutionPolicy <a href="../classes/ResolutionPolicy.html" class="crosslink">ResolutionPolicy</a> &#124; <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The resolution policy desired


##### setViewPortInPoints

Sets view port rectangle with points.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:829](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L829) |

###### 参数列表
- x <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- y <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- w <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> width
- h <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> height


##### setScissorInPoints

Sets Scissor rectangle with points.

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:845](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L845) |

###### 参数列表
- x <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- y <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- w <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
- h <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 


##### isScissorEnabled

Returns whether GL_SCISSOR_TEST is enable

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Boolean" class="crosslink external" target="_blank">Boolean</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:874](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L874) |



##### getScissorRect

Returns the current scissor rectangle

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Rect.html" class="crosslink">Rect</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:883](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L883) |



##### setViewName

Sets the name of the view

| meta | description |
|------|-------------|
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:903](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L903) |

###### 参数列表
- viewName <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 


##### getViewName

Returns the name of the view

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/String" class="crosslink external" target="_blank">String</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:914](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L914) |



##### getViewPortRect

Returns the view port rectangle.

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Rect.html" class="crosslink">Rect</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:923](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L923) |



##### getScaleX

Returns scale factor of the horizontal direction (X axis).

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:932](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L932) |



##### getScaleY

Returns scale factor of the vertical direction (Y axis).

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:941](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L941) |



##### getDevicePixelRatio

Returns device pixel ratio for retina display.

| meta | description |
|------|-------------|
| 返回 | <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:950](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L950) |



##### convertToLocationInView

Returns the real location in view for a translation based on a related position

| meta | description |
|------|-------------|
| 返回 | <a href="../classes/Vec2.html" class="crosslink">Vec2</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:959](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L959) |

###### 参数列表
- tx <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The X axis translation
- ty <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Number" class="crosslink external" target="_blank">Number</a> The Y axis translation
- relatedPos <a href="https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Object" class="crosslink external" target="_blank">Object</a> The related position object including "left", "top", "width", "height" informations


##### _getInstance



| meta | description |
|------|-------------|
| 返回 | <a href="../classes/View.html" class="crosslink">View</a> 
| 定义于 | [https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js:1001](https:/github.com/cocos-creator/engine/blob/master/cocos2d/core/platform/CCView.js#L1001) |




