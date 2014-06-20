request
===============

ajax请求代理，只有code为100才返回success，其余返回fail, 会自动加上token，可以通过tbtx.tokenName定义cookie名

::

    tbtx.require("request", function(request) {
        var data = {id: 123};
        request(url, data).done(function(response) {

        }).fail(function(code, response) {

        });
    });