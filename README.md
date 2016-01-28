# jquery.slide.js
jquery轮播插件

1、轻量级轮播插件，源码不超过10kb，压缩后不超过5kb

2、支持设置一次性轮播数量

3、不提供控制UI，只提供相关api，UI完全由用户自定义


### 基本使用
#### html
```
<div class="img-box">
    <ul class="slider">
        <li>
            <img src="../../Content/images/view1.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view2.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view3.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view4.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view5.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view6.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view7.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view8.jpg" />
        </li>
        <li>
            <img src="../../Content/images/view9.jpg" />
        </li>
    </ul>
    <div class="oper-box">
        <input type="button" class="btnPrev" value="前" />
        <input type="button" class="btnNext" value="后" />
        <div class="indexBox">
            <a href="javascript:;" class="active">1</a>
            <a href="javascript:;" class="">2</a>
            <a href="javascript:;" class="">3</a>
        </div>
    </div>

</div>
```

#### css
```
<style>
    html, body, div, ul, li { margin: 0; padding: 0; }
    ul { list-style-type: none; }
    .intro { text-align: center; }
    .img-box { width: 690px; height: 130px; margin: 10px auto; }
        .img-box li { width: 225px; height: 130px; float: left; overflow: hidden; margin: 0 3px; }
        .img-box img { width: 225px; height: 130px; }
    .oper-box { text-align: center; }
    .indexBox { margin-top: 20px; }
        .indexBox a { width: 10px; height: 10px; border: 1px solid #0094ff; padding: 3px; }
        .indexBox .active { background: #000; color: #fff; }
</style>
```

#### script
```
<script src="lib/jquery-1.10.2.min.js"></script>
<script src="../src/jquery.slide.js"></script>
<script>
    $(".slider").slide({
        "switchTime": "3000",
        "indexBoxSelector": ".indexBox",
        "btnLeftSelector": ".btnPrev",
        "btnRightSelector": ".btnNext",
        "indexClass": "active",
        "perScrollCount": 3
    });
</script>
```
### Demo

1.<a href="http://luopq.com/demo/slide/examples/index.html" target="_blank">Demo1</a>

2.<a href="http://luopq.com/demo/osum/index.html" target="_blank">Demo2</a>


### Options
| 参数名 | 类型 | 默认值 | 描述 |
| ----  | ---- | ----- | ----|
|switchTime| number|5000|轮播切换间隔时间，单位毫秒|
|speed|number| 400 | 轮播动画时间，单位毫秒|
|perScrollCount|number|1|每次轮播数量|
|indexBoxSelector|string|".indexBox"|图片索引列表容器的选择器|
|btnPrevSelector|string|".btnPrev"|向前按钮选择器|
|btnNextSelector|string|".btnNext"|向后按钮选择器|
|indexClass|string|null|当前索引样式|
|bindHover|boolean|true|是否绑定轮播时的元素的Hover事件，绑定后，鼠标移上去将不轮播|
|onInit|function|null|轮播组件初始化的回调函数，其中this指向轮播元素本身|
|onBeforeChange|function|null|轮播切换前的回调，其中this指向当前轮播项，含有一个参数指向当前轮播项索引|
|onChanged|function|null|轮播切换后的回调，其中this指向当前轮播项，含有一个参数指向当前轮播项索引|
|delay|number|0|轮播动画的延迟时间，单位毫秒|