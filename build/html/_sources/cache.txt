cache
===============

* get/set/remove/getAll/clear

::

    var cache = new tbtx.Cache();
    cache.get/set/...

* data(key[, value])/removeData(key)

::
    // 实际上内部使用的是cache的一个实例
    tbtx.data()
    tbtx.removeDate()

目前默认data的为当前的url信息

    tbtx.data("urlInfo")

当调用userCheck接口登陆成功之后会 data user和userName