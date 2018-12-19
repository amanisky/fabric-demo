### Object
+ transparentCorners 控件是否透明
+ transformMatrix 对象的矩阵数组
+ calcTransformMatrix() 计算对象的矩阵
+ calcOwnMatrix() 计算对象自身的矩阵
+ setCoords() 重新计算控件的位置

### fabric
+ 方法
  + loadSVGFromURL

### ActiveSelection
+ toGroup() 将选区变成组
+ toActiveSelection() 将组变成选区

### Canvas
+ 方法
  + getActiveObject() 获取画布上的选中对象
  + getActiveObjects() 获取画布上选中的多个对象
  + requestRenderAll() 
  + renderAll() 呈现顶部画布和辅助容器画布（同步操作）
  + setWidth()
  + setHeight()
  + setBackgroundColor()
  + setBackgroundImage()
  + setActiveObject('xx') 默认选中某个对象
  + discardActiveObject() 取消选中
  + getWidth()、setWidth()、getHeight()、setHeight()
  + setDimensions
+ 属性
  + imageSmoothingEnabled 是否开启图片平滑处理；浏览器中默认开启
  + enableRetinaScaling 启用克隆图像的视网膜缩放
  + stopContextMenu 是否取消鼠标右键默认事件
  + fireRightClick 画布是否可以触发右键单击事件
  + renderOnAddRemove
+ 事件
  + 对象变化
    + object:moving 当画布上有对象移动时触发
    + object:moved 当画布上对象移动完成后触发
    + object:scaling 当画布上有对象缩放时触发
    + object:rotating 当画布上有对象旋转时触发
    + object:scaled 当画布上对象缩放完成后触发
    + object:rotated 当画布上对象旋转完成后触发
    + before:transform 当点击画布上对象就会触发（转换之前触发）
    + object:modified 对象发生变化后触发
    + object:added 对象被添加到画布后触发
    + object:removed 对象从画布移除后触发
    + after:render canvas 画布被重新渲染之后触发
    + object:skewing -------
    + object:skewed --------
  + 选区变化
    + before:selection:cleared 清除选区之前触发
    + selection:cleared 选区被清除后触发
    + selection:created 选取被创建时触发
    + selection:updated 选区更新后触发（按住 shift 可添加或移除选区中对象）
  + 鼠标事件
    + mouse:up:before 当鼠标在画布弹起前触发
    + mouse:up 当鼠标在画布弹起触发
    + mouse:down:before 当鼠标在画布上按下前触发
    + mouse:down 当鼠标在画布上按下触发
    + mouse:move:before 当鼠标在画布上移动前触发
    + mouse:move 当鼠标在画布上移动触发
    + mouse:dblclick 在画布上双击鼠标触发
    + mouse:wheel 在画布上滚动鼠标滚轮触发
    + mouse:over 当鼠标移动到对象上方时触发
    + mouse:out 当鼠标移出对象时触发
  + 拖拽事件
    + dragenter 画布之外的某元素进入画布时触发
    + dragover 画布之外的某元素在画布上方时触发
    + dragleave 画布之外的某元素离开画布时触发
    + drop 某元素在画布内放下时触发

### Util
+ 方法
  + transformPoint
  + loadImage
  + groupSVGElements
  + degreesToRadians 度转弧度
  + getRandomInt 获取随机数

### Image
+ 方法
  + setPositionByOrigin(pos, originX, originY) 设置对象的位置，同时考虑对象的原点
  + fromURL

### Text、IText、Textbox
+ 区别
  + Text 不可输入
  + IText 可输入
  + Textbox 可输入并根据空格换行
+ 属性
  + text.styles = {...} 设置对象样式  
+ 方法
  + setSubscript() 将选中字符设置为下标
  + setSuperscript() 将选中的字符设置为上标
  + setSelectionStyles() 设置选中字符的样式
  + removeStyle() 移除指定属性样式

### 文件说明
+ 01、对选中文字处理：上标、下标、清除
+ 02、事件
+ 03、设置 canvas 背景图、取消鼠标右键默认行为等
+ 04、设置字体
+ 05、复制粘贴
+ 06、选区转组、组转选区
+ 07、**图形变换了，controls 也得做相应变换**
+ 08、根据图形边界判断是否与另一个图形相交
+ 09、clipTo 动画示例
  + https://developer.mozilla.org/zh-CN/docs/Web/API/CanvasRenderingContext2D
+ 10、网格
+ 11、读取 SVG 文件
+ 12、使用图案填充图形
+ 13、**修改对象时，会在原来的位置留下虚线框**
+ 14、**让拖动的对象透明度变化（objectCaching 的应用）**
+ 15、**缩放、移动画布**
+ 16、与画布外的对象交互
+ 17、**扩展自定义属性，用来传递数据**
+ 18、**加载SVG不分组**
+ 19、undo、redo
+ 20、撤销、重做
+ 21、网格放入组中，方便显示和隐藏
+ 22、保存为图片
+ 23、**svg base64 动态网格**
+ 24、**使用生成的网格作为画布背景平铺**
  + 参考地址：http://fabricjs.com/test/svg_export/bg_patterns_gradients.html

### 重点
+ 图形变换了，controls 也得做相应变换；否则就会出现错位
+ 基于 angularjs 很全面的案例：http://fabricjs.com/kitchensink
+ fabricjs ellipsis text：https://github.com/fabricjs/fabric.js/issues/4000

### 官方示例
+ 字体上标、下标
  + http://fabricjs.com/super-sub-script
+ 事件
  + http://fabricjs.com/events
+ 复制、粘贴
  + http://fabricjs.com/copypaste
+ 选区管理
  + 选区 -> 组
  + 组 -> 选区
  + 设置默认选区
  + 全选
  + 丢弃选区
  + http://fabricjs.com/manage-selection
+ 矩阵转换
  + http://fabricjs.com/matrix-transformation
+ 自定义控件
  + http://fabricjs.com/controls-customization
+ 独立控件
  + http://fabricjs.com/controls
+ 自由绘图
  + http://fabricjs.com/freedrawing
+ 图形边界交叉处理
  + http://fabricjs.com/intersection
+ 粘贴图片到画布
  + https://codepen.io/Nikki0417/pen/YYJKbQ  


### 参考链接
+ 画图工具
  + http://zwibbler.com/
  + http://smashinghub.com/10-best-html5-sketching-and-drawing-tools-for-designers.htm
+ 什么时候需要调用 setCoords 方法
  + https://github.com/fabricjs/fabric.js/wiki/When-to-call-setCoords
+ ViewBox
  + https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute/viewBox
+ "生动"讲解——矩阵的空间变换
  + https://blog.csdn.net/a396901990/article/details/44905791
+ 矩阵乘法
  + https://zh.wikipedia.org/wiki/矩陣乘法
+ 转置矩阵
  + https://zh.wikipedia.org/wiki/转置矩阵
+ 通过按钮缩放、移动画布
  + http://jsfiddle.net/dudih/y0z33gym/  
+ canvas自适应屏幕大小：https://www.cnblogs.com/mihoutaoguniang/p/5998511.html
+ jsfiddle frabic 案例
  + **http://jsfiddle.net/user/softvar/fiddles/**
  + **http://jsfiddle.net/user/fabricjs/fiddles/**
+ 实现下载
  + **http://41j.com/blog/2015/01/creating-svg-javascript-using-fabricjs-downloading-locally/**
+ undo、redo
  + **https://jsfiddle.net/tazehale/q2mz23xb/**  
+ 读取 svg 不分组的另一种实现方式
  + http://www.independent-software.com/loading-an-svg-image-with-fabric-js.html
+ 在画布上绘制圆
  + http://jsfiddle.net/8u1cqasa/17/  