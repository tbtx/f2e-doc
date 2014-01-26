miiee
===============

蜜儿相关

* miieeJSToken()

* userCheck(callSuccess, callFailed, isTemp)

* shareToSinaWB(selecotr, title, url, pic, site, uid)

* Request(url[, data[, successCode]])

对于使用jtoken的请求进行了一个代理，返回promise

success(response)

fail(code, response)

success是返回码为100时，其余均为失败(其中客户端没有请求成功为-1)，如果正在处理中，则notify(-2)后返回promise

* initMiiee()

加载m和base

* bingo(bingoRange, range)

概率选中, 用于概率执行某操作

从1开始记

如70%的概率则为 bingoRange 70, range 100，或者传入7, 10

* addToFavourite(title, url)

加入收藏夹