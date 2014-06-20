uri
===============

uri相关

* param(o, sep, eq, serializeArray)

对象转为query字符串, =号和?号都可以自定义

* unparam(str, sep, eq)

query字符串转为对象, =号和?号都可以自定义

* Query类

提供查询字符串的相关操作

::

    var query = new Query("name=123&age=12");

    query.get("name") => 123
    query.get() => {name: 123, age: 12}
    query.set(key, value)
    query.remove(key)
    query.add(key, value)
    query.toString() => 返回新的查询字符串

* Uri类

提供url解析

Uri.getComponents(uri)

::

    解析uri，返回uri信息，uri默认为location.href
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

* isUri(uri)

判断是否为uri

* parseUri(uri)

相当于 Uri.getComponents(uri)

* getFragment(uri)

获取锚点值

* get/set/remove/add QueryParam

获取/设置/删除/增加查询参数，url可作为第一个或最后一个参数传入

* getQueryParam(name)

返回解析url的查询字符串的对象，如果提供name，则返回name的值

* addQueryParam(name, value)/addQueryParam(object)

对一个url增加查询参数，返回增加后的url

如果有多个参数要增加可以传入一个对象

* removeQueryParam(names)

对一个url删除查询参数，返回删除参数后的url, names可以为数组或键
