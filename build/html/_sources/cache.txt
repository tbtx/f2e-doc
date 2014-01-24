cache
===============

* get/set/remove/getAll/clear

    var cache = new tbtx.Cache();
    cache.get/set/...

* data(key[, valye])/removeData(key)

实际上使用的是cache的一个实例

目前默认data的为当前的url信息

    tbtx.data("urlInfo")