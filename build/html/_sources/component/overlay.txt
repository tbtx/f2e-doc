overlay
===============

overlay 背景遮罩层

依赖jquery和tbtx.js

base/js/component/overlay.js

tbtx.Overlay 全屏遮罩

tbtx.Mask 背景遮罩

    // 获取overlay实例
    var o = new tbtx.Overlay(option);

    o.show();

    o.hide();

option
------

    element: dom元素

    or

    template: "<div></div>"  // 通过模板生成

    width: null,

    height: null,

    className: "tbtx-mask",

    // 基本属性
    visible: false,

    parentNode: DEFAULT_PARENT_NODE,

    // 定位配置
    align: {

        // element 的定位点，默认为左上角
        selfXY: [ 0, 0 ],

        // 基准定位元素，默认为当前可视区域
        baseElement: VIEWPORT,

        // 基准定位元素的定位点，默认为左上角
        baseXY: [ 0, 0 ]

    },

    // 是否点击关闭遮罩
    hideOnClick: false

    zIndex

    opacity

    backgroundColor