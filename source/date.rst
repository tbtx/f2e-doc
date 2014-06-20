date
===============

日期相关

date均可以为字符串，数字或者date对象

* formatDate([format[, date]])

"Y-m-d h:i:s" 按format格式化日期

::

    /*
     * 将日期格式化成字符串
     *  Y - 4位年
     *  y - 2位年
     *  M - 不补0的月,
     *  m - 补0的月
     *  D - 不补0的日期
     *  d - 补0的日期
     *  H - 不补0的小时
     *  h - 补0的小时
     *  I - 不补0的分
     *  i - 补0的分
     *  S - 不补0的秒
     *  s - 补0的秒
     *  毫秒暂不支持
     *  @return：指定格式的字符串
     */

* normalDate(date)

将date转为对象，包含Y-M-D-H-I-S-y-m-d-h-i-s

* diffDate(date1, date2)

计算两个日期只差，输出天/小时/分/秒

