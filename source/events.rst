events
===============

提供基本的事件添加、移除和触发功能。

默认已经mixTo tbtx

并且可以通过tbtx.on("window.resize")和tbtx.on("window.scroll")监听throttle过后的函数

使用 Events 有两种方式，一种是直接实例化：

    var object = new tbtx.Events();

    object.on('expand', function() {
        alert('expanded');
    });

    object.trigger('expand');

另一种是将 Events 混入（mix-in）到其他类中：

    function Dog() {}

    tbtx.Events.mixTo(Dog);

    Dog.prototype.sleep = function() {
        this.trigger('sleep');
    };

    var dog = new Dog();

    dog.on('sleep', function() {
        alert('狗狗睡得好香呀');
    });

    dog.sleep();

通过new tbtx.Class创建的类，或者对象或类classify之后, 去Implements Events，也可以获得on/off/trigger的能力

    var o = {};

    tbtx.classify(o);

    o.Implements(tbtx.Events);   // o对象即拥有了on和off方法

    // 或者

    var App = new tbtx.Class();

    App.Implements(tbtx.Events)