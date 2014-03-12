msg
===============

消息Widget

warning error info debug success

tbtx.MSG.error/warning/success/info/debug(msg)

或者直接使用tbtx.error/warning/success/info/debug


* broadcast

另一种消息提醒

::

    // 消息内容， 停留时间（默认4000），消息位置（top/center/bottom）
    tbtx.broadcast(msg, duration, direction)