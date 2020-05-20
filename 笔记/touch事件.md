# touch事件

## 首先 touch 包含三类事件，它们分别是：touchstart、touchmove、touchend 

**touchstart：手指触摸到一个 DOM 元素时触发。**

**touchmove：手指在一个 DOM 元素上滑动时触发。**

**touchend：手指从一个 DOM 元素上移开时触发。**

## 这三个事件又分别对应三个相同的触摸列表：

**touches: 当前屏幕上所有触摸点的列表;**

**targetTouches: 正在触摸当前 DOM 元素上的触摸点的一个列表;**

**changedTouches: 涉及当前(引发)事件的触摸点的列表**

---------------------------------

通过一个例子来区分一下触摸事件中的这三个属性：

1. 用一个手指接触屏幕，触发事件，此时这三个属性有相同的值。

2. 用第二个手指接触屏幕，此时，`touches`有两个元素，每个手指触摸点为一个值。当两个手指触摸相同元素时，==`targetTouches`==和==`touches`==的值==相同==，否则==`targetTouches`== 只有==一==个值。`changedTouches`此时只有一个值，为第二个手指的触摸点，因为第二个手指是引发事件的原因

3. 用两个手指同时接触屏幕，此时``changedTouches``有两个值，每一个手指的触摸点都有一个值

4. 手指滑动时，三个值都会发生变化

5. 一个手指离开屏幕，``touches``和``targetTouches``中对应的元素会同时移除，而``changedTouches``仍然会存在元素。

6. 手指都离开屏幕之后，``touches和targetTouches``中将不会再有值，``changedTouches``还会有一个值，
   此值为最后一个离开屏幕的手指的接触点。

**2. 触点坐标选取**

**touchstart和touchmove使用:**``e.targetTouches[0].pageX`` 或 ``(jquery)e.originalEvent.targetTouches[0].pageX``

**touchend使用:** ``e.changedTouches[0].pageX`` 或 ``(jquery)e.originalEvent.changedTouches[0].pageX``

**3.touchmove事件对象的获取**

想要在touchmove:function(e,参数一)加一个参数，结果直接使用e.preventDefault()就会 e 报错，处理方法为使用arguments[0]获取event参数
```js
touchmove:function(e,参数一){
　　var e=arguments[0]
      　　e.preventDefault()
}
```
-------------------------------------

**事件对应的三个列表虽然名字不一样，但是它们里面装的东西都是差不多的，包含了当前事件的一些相关信息，比如：一些坐标信息。**

```
TouchList {0: Touch, length: 1}
length:1 //只有一个触摸点
0:Touch
    clientX:65 // 触摸点在浏览器窗口中的横坐标
    clientY:18 // 触摸点在浏览器窗口中的纵坐标
    force:1 // 触摸点压力大小
    identifier:0 // 触摸点唯一标识（ID）
    pageX:65 // 触摸点在页面中的横坐标
    pageY:18 // 触摸点在页面中的纵坐标
    radiusX:11.5 // 触摸点椭圆的水平半径
    radiusY:11.5 // 触摸点椭圆的垂直半径
    rotationAngle:0 // 旋转角度
    screenX:560 // 触摸点在屏幕中的横坐标
    screenY:175 // 触摸点在屏幕中的纵坐标
target:div#touchLog 触摸目标
__proto__:Touch
__proto__:TouchList
```



> ###### 来自 mozilla
>
> 1.Touch.identifier：此 Touch 对象的唯一标识符。 一次触摸动作(我们指的是手指的触摸)在平面上移动的整个过程中，该标识符不变。 可以根据它来判断跟踪的是否是同一次触摸过程，此值为只读属性。
>
> 2.Touch.screenX：触点相对于屏幕左边沿的X坐标。只读属性。
>
> 3.Touch.screenY：触点相对于屏幕上边沿的Y坐标。只读属性。
>
> 4.Touch.clientX：触点相对于可见视区(visual viewport)左边沿的X坐标。不包括任何滚动偏移。只读属性。
>
> 5.Touch.clientY：触点相对于可见视区(visual viewport)上边沿的Y坐标。不包括任何滚动偏移。只读属性。
>
> 6.Touch.pageX：触点相对于HTML文档左边沿的X坐标。当存在水平滚动的偏移时，这个值包含了水平滚动的偏移。只读属性。
>
> 7.Touch.pageY：触点相对于HTML文档上边沿的Y坐标。当存在水平滚动的偏移时，这个值包含了垂直滚动的偏移。只读属性。
>
> 8.Touch.radiusX：能够包围用户和触摸平面的接触面的最小椭圆的水平轴(X轴)半径。这个值的单位和 screenX 相同。只读属性。
>
> 9.Touch.radiusY：能够包围用户和触摸平面的接触面的最小椭圆的垂直轴(Y轴)半径。这个值的单位和 screenY 相同。只读属性。
>
> 10.Touch.rotationAngle：它是这样一个角度值：由radiusX 和 radiusY描述的正方向的椭圆，需要通过顺时针旋转这个角度值，才能最精确地覆盖住用户和触摸平面的接触面。只读属性。
>
> 11.Touch.force：手指挤压触摸平面的压力大小，从0.0(没有压力)到1.0(最大压力)的浮点数。只读属性。
>
> 12.Touch.target：当这个触点最开始被跟踪时(在 touchstart  事件中)，触点位于的HTML元素。哪怕在触点移动过程中，触点的位置已经离开了这个元素的有效交互区域，或者这个元素已经被从文档中移除。需要注意的是，如果这个元素在触摸过程中被移除，这个事件仍然会指向它，但是不会再冒泡这个事件到 window 或 document  对象。因此，如果有元素在触摸过程中可能被移除，最佳实践是将触摸事件的监听器绑定到这个元素本身，防止元素被移除后，无法再从它的上一级元素上侦测到从该元素冒泡的事件。只读属性。