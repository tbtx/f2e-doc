request
===============

* tbtx.loadCss/loadScript(url, callback, charset)

url可以是miee/js/m.js，会自动加上静态文件前缀的url

加载css,js, 返回deferred对象，即可以使用

::

    tbtx.loadScript().done/fail/always/then

对于 loadScript,

url可以是一个数组，会按照数组中的脚本顺序加载，全部加载完成执行callback


loader
===============

* tbtx.require(names, callback, baseUrl)

加载组件，如tbtx.require("popup", function(){}), 会自动处理依赖引入overlay和popup

* tbtx.Loader.config()

可以配置的项有：

::

    // 默认在组件目录， 一般不需要处理，特殊情况请在require时指定baseUrl
    baseUrl: S.staticUrl + "/base/js/component/",

    // 别名配置，与path配合，配置后可以直接require("jquery")
    alias: {
        "jquery": "jquery/jquery-1.8.3.min.js",
        "handlebars": "miiee/handlebars.js",
        "easing": "plugin/jquery.easing.1.3.js"
    },

    // 路径配置
    paths: {
        miiee: '../../../miiee/js',
        plugin: '../plugin',
        gallery: '../gallery',
        jquery: '../jquery'
    },

    // 依赖关系配置
    deps: {
        // 修正页面JS已引入的状态
        drop: "overlay",
        popup: "overlay",
        tip: "drop",
        templatable: "handlebars",
        autocomplete: ["overlay", "templatable"]
    }