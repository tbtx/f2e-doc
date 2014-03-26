uri
===============

uri相关

* Query类

提供查询字符串的相关操作

::

    var query = new Query("name=123&age=12");

    query.get("name") => 123
    query.get() => {name: 123, age: 12}
    query.keys()
    query.set(key, value)
    query.remove(key)
    query.add(key, value)
    query.toString() => 返回新的查询字符串

* Uri类

提供url解析

Uri.getComponents(url)

::

    解析url，返回url信息，url默认为location.href
    // 返回对象
    scheme: 协议，如http
    domain: 域名，如miiee.taobao.com
    port: 端口，如8080
    path: 路径，如/themes
    query: 查询字符串
    fragment: 锚点

Uri实例

::

    var uri = new Uri(url)
    uri.getFragment() // 获取锚点
    uri.toString() // 返回新的uri

* isUri(url)

判断是否为uri

* parseUrl(url)

相当于 Uri.getComponents(url)

* getFragment(url)

获取锚点值

* getQueryParam([name[, url]])

返回解析url的查询字符串的对象，如果提供name，则返回name的值

* addQueryParam(name, value[, url])/addQueryParam(o[, url])

对一个url增加查询参数，返回增加后的url

如果有多个参数要增加可以传入一个对象

* removeQueryParam(name[, url])

对一个url删除查询参数，返回删除参数后的url
