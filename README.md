### Object
+ transparentCorners 控件是否透明

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
+ 属性
  + imageSmoothingEnabled 是否开启图片平滑处理；浏览器中默认开启
  + enableRetinaScaling 启用克隆图像的视网膜缩放
  + stopContextMenu 是否取消鼠标右键默认事件
  + fireRightClick 画布是否可以触发右键单击事件
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
+ 07、矩阵与对象属性转换关系

### 参考链接
+ 什么时候需要调用 setCoords 方法
  + https://github.com/fabricjs/fabric.js/wiki/When-to-call-setCoords
+ canvas自适应屏幕大小：https://www.cnblogs.com/mihoutaoguniang/p/5998511.html