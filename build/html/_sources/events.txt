events
===============

提供基本的事件添加、移除和触发功能。

on/off/trigger

默认已经mixTo tbtx

使用 Events 有两种方式，一种是直接实例化：

::

    var object = new tbtx.Events();

    object.on('expand', function() {
        alert('expanded');
    });

    object.trigger('expand');

另一种是将 Events 混入（mix-in）到其他类中：

::

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