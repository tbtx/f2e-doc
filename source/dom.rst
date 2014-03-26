dom
===============

dom操作

* getWindow/getHead/getBody/getDocument

返回相应的jQuery对象

* pageHeight()/pageWidth()

返回页面总的宽高， 相当于$(window).width()/height()

* scrollX()/scrollY()

返回页面滚动的距离, 相当于$(window).scrollTop()/scrollLeft()

* viewportHeight()/viewportWidth()

返回视口的宽高，相当于$(document).width()/height()

* contains(a, b)

dom元素a是否包含dom元素b

* isInDocument(element)

判断dom元素是否在document内，也就是create但并没有插入到dom

* isInView(selector, top)

判断元素是否出现在视口内，在则返回true

top: 距离上面多少px才算在视口内，如果top为"center",则当元素完全处在屏幕正中间时才算inView

* fullViewport(selector)

让某个元素宽高等于整个视口

* fullPage(selector)

让某个元素宽高等于整个页面

* stopBodyScroll()

停止body的滚动条

* resetBodyScroll()

恢复body的滚动条

* scrollTo(number/selector)

滚动到某个位置，可以传入一个scrollTop的距离，或者一个元素的选择器

* limitLength(selector[, attr[, suffix]])

用JS限定文本的长度

如p data-max="8"

如果超过8位，则限定内容为8位加上...

attr指定属性名，默认data-max, suffix指定后缀，默认为三个点的省略号

* initWangWang()

初始化旺旺点灯, 加载旺旺和KISSY（如果KISSY没有加载的话）

* lightWangWang(selector)

旺旺点灯的另一种实现

::

    <span data-role="wangwang" data-nick="xx_tbtx" data-prompt="有事联系我"></span>
    默认data-role="wangwang"的 会被替换成旺旺的状态

* flash(selector[, flashColor[, bgColor]])

闪烁一个元素, 用于文本框为空提示 -> tbtx.flash('input')


* flyToTop(selector)

selector为context，监听selector下的.J-fly-to-top来回到顶部

没有找到.J-fly-to-top则监听在selector上

在selector上使用data-offset, 滚动大于该值则selector显示，小于该值则隐藏

* embedPlayer(allConfig)

嵌入淘宝视频