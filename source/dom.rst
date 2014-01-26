dom
===============

dom操作

* getWindow/getHead/getBody/getDocument

返回相应的jQuery对象

* loadCss(url, callback, charset)

加载css文件， 除了不支持数组，调用同下

* loadScript(url, callback, charset)

加载js, 可指定成功的回调函数,返回jQuery deferred, 可以使用loadScript(url).done(callback)

url可以是一个数组，会按照数组中的脚本顺序加载，全部加载完成执行callback

url可以是miee/js/m.js，会自动加上cdn的url

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

* flash(selector[, flashColor[, bgColor]])

闪烁一个元素, 用于文本框为空提示 -> tbtx.flash('input')


* flyToTop(selector)

selector为context，监听selector下的.J-fly-to-top来回到顶部

没有找到.J-fly-to-top则监听在selector上

在selector上使用data-offset, 滚动大于该值则selector显示，小于该值则隐藏