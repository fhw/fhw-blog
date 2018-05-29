## fixed布局
>在弹出软键盘的时候，iOS会把所有`fixed`布局的样式设置成`absolute`布局。这个时候你只要滚动一下页面，元素基本上都是定位出问题。

解决方案：让子元素滚动，`fixed`元素放到滚动元素以外，使用`absolute`布局
## 滑动不顺畅
在滚动元素添加这个样式：
```
-webkit-overflow-scrolling: touch
```
## 点击延迟300ms
解决方案`fastclick`插件

## 点击没反应
>在某些情况下iOS非点击元素是无法绑定点击事件的

解决方案：
```
/*这个还没实践过*/
cursor:pointer
```

## 数字被识别为手机号码
解决方案：
```
<meta name="format-detection" content="telephone=no" />
```

# 未实践
`localStorage`在浏览器开启无痕模式下iOS会抛异常，导致js中断

## 未解之谜

 1.父元素设置固定宽度后，部分子元素字体大小不正常
