loader
===============

* tbtx.require(names, callback, baseUrl)

加载组件，如tbtx.require("popup", function(){}), 会自动处理依赖引入overlay和popup

* tbtx.Loader.config()

可以配置的项有：


    // 默认在组件目录， 一般不需要处理，特殊情况请在require时指定baseUrl
    baseUrl: S.staticUrl + "/base/js/component/",

    // 引入时使用的时间戳
    urlArgs: "2013.12.19.0",

    // 路径配置
    paths: {
        "handlebars": S.staticUrl + "/miiee/js/handlebars.js"
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